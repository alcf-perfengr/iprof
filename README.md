# iprof
Stupid wrapper arround Opencl-intercept-layer.
Get some tinming and API trace.

For now work with OpenMP, SYCL, DPC++, OpenCL. (aka all programing model with an OpenCL backend)

## Usage
```
iprof a simple wrapper arrount Opencl-intercept-layer
Usage:
 /soft/debuggers/iprof/iprof -h | --help
 /soft/debuggers/iprof/iprof [-v | --verbose] [-a | --asm] <application> <application-arguments>

   -h --help          Show this screen.
   -v, --verbose      Display all the OpenCL command excuted and their arguments.
   -a, --asm          Dump in your current directory the assembly for all your kernels.

 Example:
 /soft/debuggers/iprof/iprof ./a.out

 For more informations about Opencl-intercept-layer see
   https://github.com/intel/opencl-intercept-layer/blob/master/docs/controls.md
```

###

```
$iprof ./a.out

Total Enqueues: 7


Host Performance Timing Results:

Total Time (ns): 833533585

                                                                    Function Name,  Calls,     Time (ns), Time (%),  Average (ns),      Min (ns),      Max (ns)
                                                                 clCompileProgram,      1,          1008,    0.00%,          1008,          1008,          1008
                                                                   clCreateBuffer,      6,         20622,    0.00%,          3437,          1858,          8004
...


Device Performance Timing Results for Intel(R) Gen9 HD Graphics NEO:

Total Time (ns): 705758

                                          Function Name,  Calls,     Time (ns), Time (%),  Average (ns),      Min (ns),      Max (ns)
__omp_offloading_36_80253019__Z18vecadd_gpu_offloadv_l6,      1,        693663,   98.29%,        693663,        693663,        693663
                                    clEnqueueReadBuffer,      1,          1807,    0.26%,          1807,          1807,          1807
                                   clEnqueueWriteBuffer,      5,         10288,    1.46%,          2057,          1721,          2641
```
