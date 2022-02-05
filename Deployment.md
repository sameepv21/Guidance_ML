# Pre-steps
* The following steps should be done on both server and client side prior to buysing aws ec2 instance.
* Create a .env file.
    * Currently write localhost as the ip address and port number on which the server/node/express backend would be running.
    * Write hostname and password for mysql backend if using mysql, else the link of mongodb atlas if using mongodb.
* Then, make the required changes in both frontend as well as backend.
    * Use "dotenv" package of npm for backend.
    * Use REACT_APP_ as the prefix of env variables for frontend.
    * To access env variables, use process.env.<VARAIBLE_NAME>
* Delete package-lock.json file.

# Steps for NGINX
* Set Up AWS Instance
    * Use EC2 with LTS Ubuntu Version with SSD, General Purpose 64 bit X86 processor.
    * Use t2.micro (for free tier)
    * Under storage section, add 30gb storage which is free under free tier.
    * Under configure security group, add All traffic for port 0-65535.
    * Also add 0.0.0.0/0 under source for all traffic.
    * Now either choose existing ssh key pair or create new and follow the instructions.
* SSH Into the server
    * In VSCODE, set up ssh config using IdentityFile which is a .pem file for aws.
    * Initialize root user using sudo -i command.
* Set up firewall
    * See the app list. There must be an OpenSSH in the list.
    * Add OpenSSH in the list
    * Enable Firewall
    * Check its status
* Install build-essentials
* Install nodejs and npm
    * This step further contains a lot of steps.
    * You need to install noderesources using curl
        * curl -sL https://deb.nodesource.com/setup_12.x | sudo -E bash -
        * apt-get install nodejs
    * Check your node and npm version.
    * If your npm version is less than 7, then perform the following command which installs the latest version of npm which is required.
        * npm install -g npm
* Get your domain name from freenom for free
    * Configure it by clicking manage domain in service > my domains
    * Under the tab of manage freenom DNS, provide the public ipv4 address of your server with Type = A.
    * Click on save changes to finalize your domain name.
* Clone the repository which you want to deploy.
* Perform basic inspection
    * Install all dependences using npm install on both frontend and backend
    * Create .env file for both sides of code.
    * Copy and paste the contents of your local env file into server's env file and make the required changes in IP address or domain name etc.
    * Once done that, make sure that both server as well client side code utilized links from .env file only.
* Build the react application (Make sure you are inside your react application folder in server terminal).
* Install nginx
* Add Rule for nginx for firewall.
    * There are 3 applications for nginx.
    * You can select Nginx Full and add it to firewall similar to OpenSSH.
* Configure Default Nginx
    * Start NGINX and see the status of nginx to ensure that it is working.
    * Open your ip address in your browser. You should be able to see default page of nginx.
    * Change Contents of /var/www
        * Delete the contents of /var/www which is the default directory where **build** is placed.
        * Copy all the contents of build folder created earlier into this directory.
        * Note that if you want you can create another directory here and copy all contents of build folder there.
        * But then make sure that you reflect the similar changes in nginx config file which configured below.
    * Change default configuration of nginx
        * Delete the contents inside /etc/nginx/sites-enabled folder.
            * Note that here we are deleting the contents of **sites-enabled** and **not of sites-available**
        * Open /etc/nginx/sites-available/default in any text editor
        * Delete the comments if any.
        * Change the root path to where your index.html file is located i.e /var/www.
        * **Link sites-available** and sites-enabled from the command provided below.
        * Test for syntax error (perform config test) in nginx and restart nginx.
        * By now this is what your configuration file should contain
            * ```sh
              server {
                    listen 80 default_server;
                    listen [::]:80 default_server;

                    root /var/www/warehouse;
                    index index.html;

                    server_name warehouse-management.ml www.warehouse-management.ml;

                    location / {
                            try_files $uri $uri/ =404;
                    }
              }
              ```
            * **Please make sure to change the path of root according to the folder in which index.html file is located.**
            * **Also, change server_name with your domain name.**
        * Now add another location (In my case "/backend") to access express services
        * ```sh
          location /backend {
              proxy_pass http://localhost:5000;
            proxy_http_version 1.1;
            proxy_set_header Upgrade $http_upgrade;
            proxy_set_header Connection 'upgrade';
            proxy_set_header Host $host;
            proxy_cache_bypass $http_upgrade;
          }
          ```
        * **Change the port according to where your express backend is running.**
    * Test configuration of nginx and restart it.
* Enter your domain name in your browser (Your raw site, without backend should be up and running in production environment. Note that this may take upto 30 min or so).
* Configure Backend
    * Make sure your current directory is backend.
    * Perform prelimnary inspection whether all the routes are using .env variables or not and change them wherever necessary.
    * Install all dependecies.
    * Install pm2 globally (Command Given Below)
    * Start pm2.
    * Configure mysql
        * Install mysql-server (Command Given Below)
        * Run the following command to confirm that defualt password is "root".
            * mysql -u root -p (Prompt to enter the password)
                * Default password is root.
        * While still inside the mysql server, run mysql script using source <PATH>
            * <PATH> includes path where your .sql file is located.
        * Run command (given below) to reconfigure your root password
* Finally, check the status of nginx and pm2 to ensure that everything is working.
* Then, enter your domain name in the browser and your site is deployed!!

# Commands
* ssh ubuntu@<ip_address>
    * Get access of server terminal
    * Use your server's IP Adrress in place of ip_address
* sudo ufw app list
    * See which applications our firewall currently allows.
* sudo ufw allow <PACKAGE_NAME>
    * Allow <PACKAGE_NAME> to access the firewall
    * Make sure to replace the package name with the name of the package as a string (if it contains space) that you want to add.
* sudo ufw enable
    * Start the firewall
* sudo ufw status
    * See which applications are allowed inside the firewall.
* sudo apt-get install build-essential
    * Installs important compilers like gcc and g++ and installs git etc.
* git clone <REPO_NAME>
    * Clones the required repository
* npm run build
    * Run this command to create an optimized production build for react application
    * This will create a build folder inside your react application folder.
* NGINX Commands
    * sudo apt-get install nginx
    * systemctl start nginx
    * systemctl status nginx
    * systemctl restart nginx
    * systemctl reload nginx
    * systemctl stop nginx
    * nginx -t (Config Test)
    * nano /etc/nginx/sites-available/<CONFIG_FILENAME>
        * Open nginx configuration file.
* ln -s /etc/nginx/sites-available/<FILE_NAME> /etc/nginx/sites-enabled/<FILE_NAME>
* pm2 Related Commands
    * npm install -g pm2
    * pm2 start --name <NAME> <ENTRY_POINT>
        * <NAME> implies any name can be given.
        * <ENTRY_POINT> implies the starting file of your express backend.
    * pm2 restart <NAME>
    * pm2 status
    * pm2 stop <NAME>
    * pm2 delete <NAME>
* sudo apt-get install mysql-server
* MySQL Commands
    * source <PATH>
    * ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'root';
    * flush privileges;