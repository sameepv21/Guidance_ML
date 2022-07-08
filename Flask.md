# Introduction
* Flask is a python based web framework allowing you to create backend ready services easily.
* Flask implements WSGI (Web server Gateway Interface) application, which is a simple calling convention for web servers to forward requests to web applications or frameworks written in python.

# Flask
* It acts as a central object and central registry for view functions, URLs, templates etc.
* Usually created inside \_\_init__.py file.
* The first and usually the most important parameter is the application name.
    * It is useful because it is used to find and locate the resources inside the application.
    * Furthermore, there are other parameters as well such as path for static folder which are used during production build.
* There is also a config method used for setting required for production, testing and debugging. For example, it is used to set secret keys for preventing unauthorized user to handle requests.
* run() method is used for starting flask project and must always be placed inside an if clause checking the name of the application passed while creating flask object.