{
	"title": "Vishnu Pedireddi",
	"description": "Defended in September 2008",
	"date": "2008-09-15",
	"status": "",
	"positions": ["Graduate Research Assistant"]
}

Worked in the lab developing real-time traffic simulation using GPGPU style computation to accelerate the autonomous agent traffic computations.

Thesis
======

*Title:* Large Scale Traffic Simulation on Graphics Hardware

*Year:* 2008

### Abstract

The use of virtual environments is interesting if it closely mimics
real world scenarios. An interesting virtual environment is
characterized by autonomous agents inhabiting the virtual world. A
large scale simulation of entities in a virtual environment introduces
dynamic activity into a virtual environment, closely resembling an
urban area or vehicles in a freeway. However, support of large scale
simulation demands high computational resources. The work presented in
this thesis addresses this issue and massively expands the scale of
traffic simulation.

The approach to massive expansion to the scale of traffic simulation
is achieved by augmenting the Central Processing Unit with additional
computational resource available from the Graphics Processing Unit or
a “GPU” in a desktop. A modern Graphics Processing Units are parallel
computational engines with up to 128 vector processors operating in
parallel. A GPU framework is designed and implemented to support
traffic simulation. A working model in a GPU follows the paradigms of
stream computing. The datastructures used in GPU framework are
textures units and vertex buffer objects. The shaders contain code
that operates on an input stream and writes output to a predetermined
initialized texture memory unit. The use of extensions such as
Framebuffer Object, Vertex Buffer Object, Transform feedback, Fragment
Shader, and Geometry Shader form an integral part in functioning of
the GPU subsystem.

The framework built into the GPU subsystem functions in parallel with
the CPU traffic simulation system. The data transfer between the CPU
and the GPU via the system bus is kept to minimum to reduce
latency. The GPU subsystem operates independent to its CPU built
framework. The use of GPU subsystem has massively expanded the scale
of traffic simulation by at least 100 times from 200 to 20,000
vehicles simulated in real time. This expansion is achieved in real
time. The work demonstrates the feasibility of using a Graphics
Processing Unit for computation intensive applications in real time
for massive scale up in performance of applications.

[Thesis PDF](http://www.d.umn.edu/cs/thesis/vishnu_pedireddi_ms.pdf)
