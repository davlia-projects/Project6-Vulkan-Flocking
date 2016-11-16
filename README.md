Vulkan Flocking: compute and shading in one pipeline!
======================

**University of Pennsylvania, CIS 565: GPU Programming and Architecture, Project 6**

* David Liao
  Windows 7, i7-4770 @ 3.40GHz 16GB, NVIDIA Quadro K600 4GB (SIGLAB)

- Why do you think Vulkan expects explicit descriptors for things like generating pipelines and commands? HINT: this may relate to something in the comments about some components using pre-allocated GPU memory.

Vulkan uses a memory pool that's preallocated and thus requires the developer to provide explicit descriptors to manage memory distribution.

- Describe a situation besides flip-flop buffers in which you may need multiple descriptor sets to fit one descriptor layout.

Basically whenever you have multiple sets of inputs that fit a single format. Maybe you might need to pass in multiple textures into a shader. 

- What are some problems to keep in mind when using multiple Vulkan queues?

The issue with using multiple queues is if the processes are not independent of eachother, you'll run into race conditions. Other hardware considerations might include instruction set or apis that certain hardwares might support as well as the number of queues. 

- What is one advantage of using compute commands that can share data with a rendering pipeline?

Since the memory is shared, there's very low cost in passing around data. 


### Credits

* [Vulkan examples and demos](https://github.com/SaschaWillems/Vulkan) by [@SaschaWillems](https://github.com/SaschaWillems)
