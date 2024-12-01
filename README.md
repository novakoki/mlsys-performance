In this series of blog, I am going to recap what I learned about optimizing performance in my previous work, especially for machine learning systems. And I also want to introduce some newest techniques on accelerating LLMs.

1. [Introduction](Introduction.md)
2. [Where You Are: How To Measure and Profile A Program]()
3. Where The Peak Is: How To Calculate The Theoretical Performance Upper Bound
	1. [Roofline Model]()
	2. [Get Your Own Benchmark For Hardware]()
4. What You Can Do
	1. Maximize The Utility Of Hardware
		1. [Cache Efficiency]()
		2. [Multiprocessing]()
		3. [Asynchronous]()
		4. [Pipeline]()
	2. Add or Upgrade Hardware
		1. [Heterogeneous Computing: GPU,  DSP, FPGA]()
		2. [Distributed Computing]()
		3. [NVLink and RDMA]()
	3. Less Work
		1. [Quantization]()
	4. Beyond Von Neumann
		1. [Quantum computing]()
		2. [Computing with Memory]()
5. Trending Applications
	1. [Fast Attentions]()
	2. [Distributed Training and Inference]()
6. My Previous Work
	1. [Implementing GridSample on Tensilica Vision DSP]()
	2. [Implementing Swin Transformer on CUDA]()
	3. [Building Self-Driving Data Platform]()


