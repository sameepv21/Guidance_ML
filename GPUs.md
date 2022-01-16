# GPUs
* A GPU (Graphics Processing Unit) is a specialized processor with dedicated memory that conventionally perform floating point operations required for rendering graphics.
* It is a single-chip processor used for extensive graphical and mathematical computations which frees up CPU cycles for other jobs.
* The main difference between GPUs and CPUs is that GPUs devote proportionally more transistors to ALU and fewer to caches and flow control as compared to CPUs.
* Another difference is in the way of working. CPUs process the task sequencially whereas GPUs perform the task parallelly.
* [See this](https://www.youtube.com/watch?v=-P28LKWTzrI)
> Why to use GPUs?
* They have larger number of cores, which alllows for better computation of multiple parallel processes.
> When to use GPUs?
* Memory Bandwidth (Large)
* Dataset Size (Large)
* Optimization (No)
> Which libraries in python support GPUs?
* [CuPy](https://cupy.dev/) --> Numpy on the GPU
* Jax --> Numpy on the GPU
* [RAPIDS cuDF](https://docs.rapids.ai/api/cudf/nightly/) --> Pandas on the GPU
* [RAPIDS cuML](https://docs.rapids.ai/api/cuml/nightly/) --> Scikit learn on the GPU
* [RAPIDS cuGraph](https://docs.rapids.ai/api/cugraph/stable/) --> Graphs on the GPU
* [PyTorch](https://pytorch.org/docs/stable/index.html) --> Tensors on the GPU
* Some important Links
    * [GPU Accelarated RAPIDS Library](https://www.kaggle.com/harishvutukuri/introduction-to-rapids)