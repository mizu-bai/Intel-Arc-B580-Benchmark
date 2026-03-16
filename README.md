# Intel Arc B580 Benchmark

- Author: mizu-bai
- Date: Mar 16, 2026

## Platform

BIOS Patched with [`ReBarUEFI`](https://github.com/xCuri0/ReBarUEFI).

```
mizu-bai@mizu-bai-X99:~$ fastfetch 
                             ....              mizu-bai@mizu-bai-X99
              .',:clooo:  .:looooo:.           ---------------------
           .;looooooooc  .oooooooooo'          OS: Ubuntu 25.10 x86_64
        .;looooool:,''.  :ooooooooooc          Host: X99
       ;looool;.         'oooooooooo,          Kernel: Linux 6.17.0-19-generic
      ;clool'             .cooooooc.  ,,       Uptime: 1 hour, 33 mins
         ...                ......  .:oo,      Packages: 1585 (dpkg), 11 (snap)
  .;clol:,.                        .loooo'     Shell: bash 5.2.37
 :ooooooooo,                        'ooool     Display (AOC 27"): 1920x1200 @ 60 Hz in 27" [External]
'ooooooooooo.                        loooo.    DE: GNOME 49.0
'ooooooooool                         coooo.    WM: Mutter (Wayland)
 ,loooooooc.                        .loooo.    WM Theme: Adwaita
   .,;;;'.                          ;ooooc     Theme: Adwaita [GTK2/3/4]
       ...                         ,ooool.     Icons: Adwaita [GTK2/3/4]
    .cooooc.              ..',,'.  .cooo.      Font: Cantarell (11pt) [GTK2/3/4]
      ;ooooo:.           ;oooooooc.  :l.       Cursor: Adwaita (24px)
       .coooooc,..      coooooooooo.           Terminal: /dev/pts/1
         .:ooooooolc:. .ooooooooooo'           CPU: Intel(R) Xeon(R) E5-2680 v4 (28) @ 3.30 GHz
           .':loooooo;  ,oooooooooc            GPU 1: AMD Radeon HD 7470/8470 / R5 235/310 OEM
               ..';::c'  .;loooo:'             GPU 2: ASPEED Technology, Inc. ASPEED Graphics Family
                                               GPU 3: Intel Arc B580 @ 2.85 GHz [Discrete]
                                               Memory: 2.35 GiB / 91.94 GiB (3%)
                                               Swap: 0 B / 8.00 GiB (0%)
                                               Disk (/): 72.78 GiB / 456.34 GiB (16%) - ext4
                                               Local IP (ens1): 10.250.112.220/24
                                               Locale: en_US.UTF-8
```

## Environment Setup

See [Intel(R) Arc(TM) Graphics Driver - Ubuntu*](https://www.intel.com/content/www/us/en/download/747008/intel-arc-graphics-driver-ubuntu.html)

## Info

```
$ xpu-smi discovery 
+-----------+--------------------------------------------------------------------------------------+
| Device ID | Device Information                                                                   |
+-----------+--------------------------------------------------------------------------------------+
| 0         | Device Name: Intel(R) Arc(TM) B580 Graphics                                          |
|           | Vendor Name: Intel(R) Corporation                                                    |
|           | SOC UUID: 00000000-0000-0006-0000-0000e20b8086                                       |
|           | PCI BDF Address: 0000:06:00.0                                                        |
|           | DRM Device: /dev/dri/card2                                                           |
|           | Function Type: physical                                                              |
+-----------+--------------------------------------------------------------------------------------+
```

## Base

### [`clpeak`](https://github.com/krrishnarraj/clpeak)

1.1.7

- Build from source with `gcc-15`

```
Platform: Intel(R) OpenCL Graphics
  Device: Intel(R) Arc(TM) B580 Graphics
    Driver version  : 26.05.37020.3 (Linux x64)
    Compute units   : 160
    Clock frequency : 2850 MHz

    Global memory bandwidth (GBPS)
      float   : 1228.37
      float2  : 1130.60
      float4  : 1167.10
      float8  : 1143.91
      float16 : 1054.71

    Single-precision compute (GFLOPS)
      float   : 14551.67
      float2  : 14565.96
      float4  : 14544.09
      float8  : 14501.49
      float16 : 14417.30

    Half-precision compute (GFLOPS)
      half   : 25960.55
      half2  : 28292.74
      half4  : 28918.53
      half8  : 28762.55
      half16 : 28569.94

    Double-precision compute (GFLOPS)
      double   : 910.62
      double2  : 910.00
      double4  : 908.68
      double8  : 905.93
      double16 : 900.52

    Integer compute (GIOPS)
      int   : 4504.53
      int2  : 4461.48
      int4  : 4467.12
      int8  : 4448.98
      int16 : 4365.09

    Integer compute Fast 24bit (GIOPS)
      int   : 4484.73
      int2  : 4491.41
      int4  : 4500.96
      int8  : 4512.41
      int16 : 4533.89

    Integer char (8bit) compute (GIOPS)
      char   : 21309.33
      char2  : 26322.98
      char4  : 25874.08
      char8  : 25482.99
      char16 : 25133.55

    Integer short (16bit) compute (GIOPS)
      short   : 21162.25
      short2  : 26319.22
      short4  : 25888.89
      short8  : 25500.90
      short16 : 25100.01

    Transfer bandwidth (GBPS)
      enqueueWriteBuffer              : 6.15
      enqueueReadBuffer               : 6.37
      enqueueWriteBuffer non-blocking : 6.73
      enqueueReadBuffer non-blocking  : 7.00
      enqueueMapBuffer(for read)      : 6.62
        memcpy from mapped ptr        : 10.49
      enqueueUnmap(after write)       : 6.94
        memcpy to mapped ptr          : 10.21

    Kernel launch latency : 2.30 us
```

- Build from source with `icx`

```
Platform: Intel(R) OpenCL Graphics
  Device: Intel(R) Arc(TM) B580 Graphics
    Driver version  : 26.05.37020.3 (Linux x64)
    Compute units   : 160
    Clock frequency : 2850 MHz

    Global memory bandwidth (GBPS)
      float   : 1227.92
      float2  : 1130.52
      float4  : 1167.35
      float8  : 1144.10
      float16 : 1054.54

    Single-precision compute (GFLOPS)
      float   : 14551.48
      float2  : 14566.02
      float4  : 14544.26
      float8  : 14501.41
      float16 : 14417.28

    Half-precision compute (GFLOPS)
      half   : 25959.90
      half2  : 28290.57
      half4  : 28919.66
      half8  : 28763.19
      half16 : 28571.21

    Double-precision compute (GFLOPS)
      double   : 910.61
      double2  : 910.01
      double4  : 908.67
      double8  : 905.93
      double16 : 900.51

    Integer compute (GIOPS)
      int   : 4497.35
      int2  : 4449.83
      int4  : 4441.02
      int8  : 4429.94
      int16 : 4365.75

    Integer compute Fast 24bit (GIOPS)
      int   : 4475.45
      int2  : 4496.52
      int4  : 4491.20
      int8  : 4502.07
      int16 : 4528.27

    Integer char (8bit) compute (GIOPS)
      char   : 21264.94
      char2  : 26250.99
      char4  : 25867.71
      char8  : 25483.88
      char16 : 25103.92

    Integer short (16bit) compute (GIOPS)
      short   : 21149.23
      short2  : 26257.54
      short4  : 25887.85
      short8  : 25500.52
      short16 : 25075.22

    Transfer bandwidth (GBPS)
      enqueueWriteBuffer              : 6.15
      enqueueReadBuffer               : 6.37
      enqueueWriteBuffer non-blocking : 6.73
      enqueueReadBuffer non-blocking  : 7.00
      enqueueMapBuffer(for read)      : 6.62
        memcpy from mapped ptr        : 9.13
      enqueueUnmap(after write)       : 6.93
        memcpy to mapped ptr          : 9.53

    Kernel launch latency : 2.31 us
```

### [`OpenCL-Benchmark`](https://github.com/ProjectPhysX/OpenCL-Benchmark)

v1.9

Build from source with `gcc-15`

```
.-----------------------------------------------------------------------------.
|----------------.------------------------------------------------------------|
| Device ID    0 | Intel(R) Arc(TM) B580 Graphics                             |
|----------------'------------------------------------------------------------|
|----------------.------------------------------------------------------------|
| Device ID      | 0                                                          |
| Device Name    | Intel(R) Arc(TM) B580 Graphics                             |
| Device Vendor  | Intel(R) Corporation                                       |
| Device Driver  | 26.05.37020.3 (Linux)                                      |
| OpenCL Version | OpenCL C 3.0                                               |
| Compute Units  | 160 at 2850 MHz (2560 cores, 14.592 TFLOPs/s)              |
| Memory, Cache  | 12215 MB VRAM, 18432 KB global / 128 KB local              |
| Buffer Limits  | 11605 MB global, 11883724 KB constant                      |
|----------------'------------------------------------------------------------|
| Info: OpenCL C code successfully compiled.                                  |
| FP64  compute                                         0.898 TFLOPs/s (1/16) |
| FP32  compute                                        14.423 TFLOPs/s ( 1x ) |
| FP16  compute                                        28.406 TFLOPs/s ( 2x ) |
| INT64 compute                                         0.755  TIOPs/s (1/24) |
| INT32 compute                                         4.653  TIOPs/s (1/3 ) |
| INT16 compute                                        37.999  TIOPs/s ( 2x ) |
| INT8  compute                                        47.592  TIOPs/s ( 4x ) |
| Memory Bandwidth ( coalesced read      )                        587.27 GB/s |
| Memory Bandwidth ( coalesced      write)                        475.44 GB/s |
| Memory Bandwidth (misaligned read      )                        906.59 GB/s |
| Memory Bandwidth (misaligned      write)                        399.05 GB/s |
| PCIe   Bandwidth (send                 )                          6.23 GB/s |
| PCIe   Bandwidth (   receive           )                          6.44 GB/s |
| PCIe   Bandwidth (        bidirectional)            (Gen3 x16)    6.60 GB/s |
|-----------------------------------------------------------------------------|
'-----------------------------------------------------------------------------'
```

### [`vkpeak`](https://github.com/nihui/vkpeak)

20260112

```
device       = Intel(R) Arc(tm) B580 Graphics (BMG G21)
driver       = Intel open-source Mesa driver / Mesa 25.2.8-0ubuntu0.25.10.1

fp32-scalar  = 13721.04 GFLOPS
fp32-vec4    = 9330.86 GFLOPS

fp16-scalar  = 26528.37 GFLOPS
fp16-vec4    = 24553.08 GFLOPS
fp16-matrix  = 116489.10 GFLOPS

fp64-scalar  = 800.93 GFLOPS
fp64-vec4    = 777.89 GFLOPS

int32-scalar = 3426.37 GIOPS
int32-vec4   = 3504.60 GIOPS

int16-scalar = 12615.97 GIOPS
int16-vec4   = 13300.78 GIOPS

int64-scalar = 668.57 GIOPS
int64-vec4   = 573.30 GIOPS

int8-dotprod = 49103.85 GIOPS
int8-matrix  = 231778.80 GIOPS

bf16-dotprod = 9883.26 GFLOPS
bf16-matrix  = 116411.28 GFLOPS

fp8-matrix   = 0.00 GFLOPS
bf8-matrix   = 0.00 GFLOPS

copy-h2h     = 9.79 GBPS
copy-h2d     = 9.80 GBPS
copy-d2h     = 10.13 GBPS
copy-d2d     = 196.05 GBPS
```

## HPC

### Amber 20 SYCL

Ref. [Amber20 SYCL version for Intel GPU Max Series](https://ambermd.org/GPUSupport.php)

PME STMV NPT 4fs with

```sh
$ pmemd.sycl -O -i mdin[OPT].GPU -o mdout[OPT].GPU -p /path/to/STMV/prmtop -c /path/to/STMV/inpcrd
```

`16.60 ns/day` for `mdin.GPU` and `12.20 ns/day` for `mdinOPT.GPU`, huh...

- `mdin.GPU`

```
--------------------------------------------------------------------------------
   5.  TIMINGS
--------------------------------------------------------------------------------

|  NonSetup CPU Time in Major Routines:
|
|     Routine           Sec        %
|     ------------------------------
|     Nonbond          73.67   36.15
|     Bond              0.00    0.00
|     Angle             0.00    0.00
|     Dihedral          0.00    0.00
|     Shake             0.13    0.06
|     RunMD           126.37   62.01
|     Other             3.62    1.77
|     ------------------------------
|     Total           203.78

|  PME Nonbond Pairlist CPU Time:
|
|     Routine              Sec        %
|     ---------------------------------
|     Set Up Cit           0.00    0.00
|     Build List           0.00    0.00
|     ---------------------------------
|     Total                0.00    0.00

|  PME Direct Force CPU Time:
|
|     Routine              Sec        %
|     ---------------------------------
|     NonBonded Calc       0.00    0.00
|     Exclude Masked       0.00    0.00
|     Other                0.05    0.02
|     ---------------------------------
|     Total                0.05    0.02

|  PME Reciprocal Force CPU Time:
|
|     Routine              Sec        %
|     ---------------------------------
|     1D bspline           0.00    0.00
|     Grid Charges         0.00    0.00
|     Scalar Sum           0.00    0.00
|     Gradient Sum         0.00    0.00
|     FFT                  0.00    0.00
|     ---------------------------------
|     Total                0.00    0.00

|  Final Performance Info:
|     -----------------------------------------------------
|     Average timings for last       1 steps:
|     Elapsed(s) =       0.00 Per Step(ms) =       0.45
|         ns/day =     766.01   seconds/ns =     112.79
|
|     Average timings for all steps:
|     Elapsed(s) =     208.13 Per Step(ms) =      20.81
|         ns/day =      16.60   seconds/ns =    5203.31
|     -----------------------------------------------------

|  Setup CPU time:            9.27 seconds
|  NonSetup CPU time:       203.78 seconds
|  Total CPU time:          213.05 seconds     0.06 hours

|  Setup wall time:          10    seconds
|  NonSetup wall time:      208    seconds
|  Total wall time:         218    seconds     0.06 hours

```

- `mdinOPT.GPU`

```
--------------------------------------------------------------------------------
   5.  TIMINGS
--------------------------------------------------------------------------------

|  NonSetup CPU Time in Major Routines:
|
|     Routine           Sec        %
|     ------------------------------
|     Nonbond         144.43   51.76
|     Bond              0.00    0.00
|     Angle             0.00    0.00
|     Dihedral          0.00    0.00
|     Shake             3.64    1.30
|     RunMD           124.93   44.77
|     Other             6.05    2.17
|     ------------------------------
|     Total           279.05

|  PME Nonbond Pairlist CPU Time:
|
|     Routine              Sec        %
|     ---------------------------------
|     Set Up Cit           0.00    0.00
|     Build List           0.00    0.00
|     ---------------------------------
|     Total                0.00    0.00

|  PME Direct Force CPU Time:
|
|     Routine              Sec        %
|     ---------------------------------
|     NonBonded Calc       0.00    0.00
|     Exclude Masked       0.00    0.00
|     Other                0.05    0.02
|     ---------------------------------
|     Total                0.05    0.02

|  PME Reciprocal Force CPU Time:
|
|     Routine              Sec        %
|     ---------------------------------
|     1D bspline           0.00    0.00
|     Grid Charges         0.00    0.00
|     Scalar Sum           0.00    0.00
|     Gradient Sum         0.00    0.00
|     FFT                  0.00    0.00
|     ---------------------------------
|     Total                0.00    0.00

|  Final Performance Info:
|     -----------------------------------------------------
|     Average timings for last    1000 steps:
|     Elapsed(s) =      19.62 Per Step(ms) =      19.62
|         ns/day =      17.62   seconds/ns =    4903.97
|
|     Average timings for all steps:
|     Elapsed(s) =     283.22 Per Step(ms) =      28.32
|         ns/day =      12.20   seconds/ns =    7080.59
|     -----------------------------------------------------

|  Setup CPU time:           12.91 seconds
|  NonSetup CPU time:       279.05 seconds
|  Total CPU time:          291.96 seconds     0.08 hours

|  Setup wall time:          13    seconds
|  NonSetup wall time:      283    seconds
|  Total wall time:         296    seconds     0.08 hours

```

### GROMACS 2026.0

```sh
$ gmx --version
                         :-) GROMACS - gmx, 2026.0 (-:

Executable:   /opt/gromacs-2026.0-intel-oneapi-2025.3/bin/gmx
Data prefix:  /opt/gromacs-2026.0-intel-oneapi-2025.3
Working dir:  /home/mizu-bai
Command line:
  gmx --version

GROMACS version:     2026.0
Precision:           mixed
Memory model:        64 bit
MPI library:         thread_mpi
MPI version:         built in
OpenMP support:      enabled (GMX_OPENMP_MAX_THREADS = 128)
GPU support:         SYCL (oneAPI DPC++)
NBNxM GPU setup:     super-cluster 1x2x2 / cluster 8 (cluster-pair splitting on)
SIMD instructions:   AVX2_256
CPU FFT library:     Intel MKL version 2025.0.3 Build 20251007
GPU FFT library:     Intel MKL version 2025.0.3 Build 20251007
Multi-GPU FFT:       none
RDTSCP:              enabled
TNG support:         enabled
Hwloc support:       disabled
Tracing support:     disabled
Colvars support:     enabled (version 2025-10-13)
CP2K support:        disabled
Torch support:       disabled
Plumed support:      enabled
C compiler:          /opt/intel/oneapi/compiler/2025.3/bin/icx IntelLLVM 2025.3.2
C compiler flags:    -mavx2 -mfma -Wno-missing-field-initializers -O3 -DNDEBUG
C++ compiler:        /opt/intel/oneapi/compiler/2025.3/bin/icpx IntelLLVM 2025.3.2
C++ compiler flags:  -mavx2 -mfma -Wno-reserved-identifier -Wno-missing-field-initializers -Weverything -Wno-c++98-compat -Wno-c++98-compat-pedantic -Wno-source-uses-openmp -Wno-c++17-extensions -Wno-documentation-unknown-command -Wno-covered-switch-default -Wno-switch-enum -Wno-switch-default -Wno-extra-semi-stmt -Wno-weak-vtables -Wno-shadow -Wno-padded -Wno-reserved-id-macro -Wno-double-promotion -Wno-exit-time-destructors -Wno-global-constructors -Wno-documentation -Wno-format-nonliteral -Wno-used-but-marked-unused -Wno-float-equal -Wno-cuda-compat -Wno-conditional-uninitialized -Wno-conversion -Wno-disabled-macro-expansion -Wno-unused-macros -Wno-unsafe-buffer-usage -fno-finite-math-only -Wno-cast-function-type-strict SHELL:-fiopenmp -O3 -DNDEBUG
BLAS library:        Intel MKL version 2025.0.3 Build 20251007
LAPACK library:      Intel MKL version 2025.0.3 Build 20251007
SYCL version:        oneAPI DPC++ 20260112 (libsycl 8.0.0)
SYCL compiler flags: -fsycl -fsycl-device-code-split=per_kernel -ffast-math -Wno-incorrect-sub-group-size -DSYCL2020_DISABLE_DEPRECATION_WARNINGS
SYCL linker flags:   -fsycl -fsycl-device-code-split=per_kernel -ftarget-register-alloc-mode=pvc:small
```

Remember to build with option `-DGMX_GPU_NB_CLUSTER_SIZE=8`

Run ADH Cubic with

```sh
$ gmx mdrun -v -deffnm pme_verlet -ntmpi 1 -ntomp 24 -nb gpu -pme gpu -bonded [cpu|gpu] -update gpu -pin on
```

`132.274 ns/day` for bonded cpu and `144.212 ns/day` for bonded gpu.

- bonded cpu

```
      R E A L   C Y C L E   A N D   T I M E   A C C O U N T I N G

On 1 MPI rank, each using 24 OpenMP threads

 Activity:              Num   Num      Call    Wall time         Giga-Cycles
                        Ranks Threads  Count      (s)         total sum    %
--------------------------------------------------------------------------------
 Neighbor search           1   24       1251       6.878        396.142   5.3
 Launch PP GPU ops.        1   24     198751      37.396       2154.007  28.6
 Force                     1   24     100001      22.241       1281.077  17.0
 PME GPU mesh              1   24     100001      27.050       1558.079  20.7
 PME wait for PP                                 103.589       5966.614  79.3
 Wait GPU NB local         1   24     100001       0.237         13.623   0.2
 Wait GPU state copy       1   24     222003      34.313       1976.393  26.3
 NB X/F buffer ops.        1   24       1001       0.055          3.193   0.0
 Write traj.               1   24          1       0.332         19.121   0.3
 Constraints               1   24          2       0.001          0.048   0.0
 GPU constr. setup         1   24          1       0.003          0.154   0.0
 Kinetic energy            1   24      20001       0.895         51.545   0.7
--------------------------------------------------------------------------------
 Total                                           130.639       7524.693 100.0
--------------------------------------------------------------------------------
 Breakdown of PME mesh activities
--------------------------------------------------------------------------------
 Wait PME GPU gather       1   24     100001       1.635         94.171   1.3
 Reduce GPU PME F          1   24     100001       0.025          1.462   0.0
 Launch PME GPU ops.       1   24     800008      23.863       1374.466  18.3
--------------------------------------------------------------------------------

               Core t (s)   Wall t (s)        (%)
       Time:     3134.776      130.639     2399.6
                 (ns/day)    (hour/ns)    (ms/step)  (Matom*steps/s) 
Performance:      132.274        0.181        1.306          102.709 
Finished mdrun on rank 0 Mon Mar 16 16:47:11 2026
```

- bonded gpu

```
      R E A L   C Y C L E   A N D   T I M E   A C C O U N T I N G

On 1 MPI rank, each using 24 OpenMP threads

 Activity:              Num   Num      Call    Wall time         Giga-Cycles
                        Ranks Threads  Count      (s)         total sum    %
--------------------------------------------------------------------------------
 Neighbor search           1   24       1251       6.951        400.385   5.8
 Launch PP GPU ops.        1   24     198751      29.366       1691.451  24.5
 Force                     1   24     100001       0.168          9.664   0.1
 PME GPU mesh              1   24     100001      34.793       2004.024  29.0
 PME wait for PP                                  85.032       4897.795  71.0
 Wait Bonded GPU           1   24       1001       0.006          0.336   0.0
 Wait GPU NB local         1   24     100001       0.234         13.494   0.2
 Wait GPU state copy       1   24      25253      45.205       2603.799  37.7
 NB X/F buffer ops.        1   24       1001       0.059          3.379   0.0
 Write traj.               1   24          1       0.327         18.846   0.3
 Constraints               1   24          2       0.001          0.047   0.0
 GPU constr. setup         1   24          1       0.003          0.152   0.0
 Kinetic energy            1   24      20001       1.318         75.933   1.1
--------------------------------------------------------------------------------
 Total                                           119.825       6901.818 100.0
--------------------------------------------------------------------------------
 Breakdown of PME mesh activities
--------------------------------------------------------------------------------
 Wait PME GPU gather       1   24     100001       9.248        532.674   7.7
 Reduce GPU PME F          1   24     100001       0.026          1.509   0.0
 Launch PME GPU ops.       1   24     800008      23.779       1369.638  19.8
--------------------------------------------------------------------------------

               Core t (s)   Wall t (s)        (%)
       Time:     2875.783      119.825     2400.0
                 (ns/day)    (hour/ns)    (ms/step)  (Matom*steps/s) 
Performance:      144.212        0.166        1.198          111.979 
Finished mdrun on rank 0 Mon Mar 16 16:51:27 2026
```

### LAMMPS Update 3 for Stable release 22 July 2025

Build `lammps-22Jul2025_update3` with, no idea why Intel OpenMP cannot be detected with default settings...

```sh
$ cmake ../cmake/ -DCMAKE_INSTALL_PREFIX=/opt/lammps-22Jul2025_update3-intel-oneapi-2025.3 -DCMAKE_BUILD_TYPE=Release -C ../cmake/presets/oneapi.cmake -C ../cmake/presets/most.cmake -C ../cmake/presets/kokkos-openmp.cmake -C ../cmake/presets/kokkos-sycl-intel.cmake -DPKG_VORONOI=OFF -DPKG_GPU=ON -D GPU_API=opencl -D GPU_PREC=mixed -D OpenMP_C_FLAGS="-fiopenmp" -D OpenMP_CXX_FLAGS="-fiopenmp" -D OpenMP_C_LIB_NAMES="iomp5" -D OpenMP_CXX_LIB_NAMES="iomp5"
```

Build log

```sh
-- <<< Build configuration >>>
   LAMMPS Version:   2025.7.22.3 
   Operating System: Linux Ubuntu" 25.10
   CMake Version:    3.31.6
   Build type:       Release
   Install path:     /opt/lammps-22Jul2025_update3-intel-oneapi-2025.3
   Generator:        Unix Makefiles using /usr/bin/gmake
-- Enabled packages: AMOEBA;ASPHERE;BOCS;BODY;BPM;BROWNIAN;CG-DNA;CG-SPICA;CLASS2;COLLOID;COLVARS;COMPRESS;CORESHELL;DIELECTRIC;DIFFRACTION;DIPOLE;DPD-BASIC;DPD-MESO;DPD-REACT;DPD-SMOOTH;DRUDE;EFF;ELECTRODE;EXTRA-COMMAND;EXTRA-COMPUTE;EXTRA-DUMP;EXTRA-FIX;EXTRA-MOLECULE;EXTRA-PAIR;FEP;GPU;GRANULAR;INTERLAYER;KOKKOS;KSPACE;LEPTON;MACHDYN;MANYBODY;MC;MEAM;MESONT;MISC;ML-IAP;ML-POD;ML-SNAP;ML-UF3;MOFFF;MOLECULE;OPENMP;OPT;ORIENT;PERI;PHONON;PLUGIN;POEMS;QEQ;REACTION;REAXFF;REPLICA;RHEO;RIGID;SHOCK;SPH;SPIN;SRD;TALLY;UEF;YAFF
-- <<< Compilers and Flags: >>>
-- C++ Compiler:     /opt/intel/oneapi/compiler/2025.3/bin/icpx
      Type:          IntelLLVM
      Version:       2025.3.2
      C++ Standard:  17
      C++ Flags:      -w -fsycl -fsycl-device-code-split=per_kernel -fsycl-targets=spir64   -w -fsycl -fsycl-device-code-split=per_kernel -fsycl-targets=spir64   -w -fsycl -fsycl-device-code-split=per_kernel -fsycl-targets=spir64   -w -fsycl -fsycl-device-code-split=per_kernel -fsycl-targets=spir64  -fp-model precise -Wno-tautological-constant-compare -Wno-unused-command-line-argument -O3 -DNDEBUG
      Defines:       LAMMPS_SMALLBIG;LAMMPS_MEMALIGN=64;LAMMPS_OMP_COMPAT=4;LAMMPS_GZIP;FFT_MKL;FFT_MKL_THREADS;EIGEN_NO_CUDA;LMP_OPENMP;$<BUILD_INTERFACE:LMP_KOKKOS>;FFT_KOKKOS_MKL_GPU;LMP_GPU;LMP_PLUGIN
-- C compiler:       /opt/intel/oneapi/compiler/2025.3/bin/icx
      Type:          IntelLLVM
      Version:       2025.3.2
      C Flags:       -O3 -DNDEBUG
-- <<< Linker flags: >>>
-- Executable name:  lmp
-- Executable linker flags:  -fsycl -flink-huge-device-code  -fsycl -flink-huge-device-code  -fsycl -flink-huge-device-code  -fsycl -flink-huge-device-code 
-- Static library flags:    
-- <<< MPI flags >>>
-- MPI_defines:      MPICH_SKIP_MPICXX;OMPI_SKIP_MPICXX;_MPICC_H
-- MPI includes:     /opt/intel/oneapi/mpi/2021.17/include
-- MPI libraries:    /opt/intel/oneapi/mpi/2021.17/lib/libmpicxx.so;/opt/intel/oneapi/mpi/2021.17/lib/libmpi.so;/lib/x86_64-linux-gnu/librt.a;/lib/x86_64-linux-gnu/libpthread.a;/lib/x86_64-linux-gnu/libdl.a;
-- <<< GPU package settings >>>
-- GPU API:                  OPENCL
-- GPU precision:            MIXED
-- Kokkos Devices: OPENMP;SERIAL;SYCL
-- <<< FFT settings >>>
-- Primary FFT lib:  MKL
-- Using double precision FFTs
-- Using threaded FFTs
-- Using builtin distributed FFT algorithms
-- Kokkos FFT: MKL_GPU
-- <<< Building Tools >>>
```

ReaxFF CHO system `examples/reaxff/CHO, `3.854 ns/day`.

```
$ lmp -in in.CHO -k on g 1 -sf kk -pk kokkos newton on neigh half
```

```
Performance: 3.854 ns/day, 6.227 hours/ns, 178.438 timesteps/s, 18.736 katom-step/s
85.4% CPU use with 1 MPI tasks x 1 OpenMP threads

MPI task timing breakdown:
Section |  min time  |  avg time  |  max time  |%varavg| %total
---------------------------------------------------------------
Pair    | 9.9331     | 9.9331     | 9.9331     |   0.0 | 17.72
Neigh   | 2.0915     | 2.0915     | 2.0915     |   0.0 |  3.73
Comm    | 11.442     | 11.442     | 11.442     |   0.0 | 20.42
Output  | 0.0048204  | 0.0048204  | 0.0048204  |   0.0 |  0.01
Modify  | 32.414     | 32.414     | 32.414     |   0.0 | 57.84
Other   |            | 0.157      |            |       |  0.28
```

## AI

### ncnn

20260113

[`benchncnn`](https://github.com/Tencent/ncnn/tree/master/benchmark)

```
$ ../build/benchmark/benchncnn 4 1 0 0
[0 Intel(R) Arc(tm) B580 Graphics (BMG G21)]  queueC=1[1]  queueT=2[1]
[0 Intel(R) Arc(tm) B580 Graphics (BMG G21)]  fp16-p/s/u/a=1/1/1/1  int8-p/s/u/a=1/1/1/1  bf16-p/s=1/1
[0 Intel(R) Arc(tm) B580 Graphics (BMG G21)]  subgroup=32(16~32)  ops=1/1/1/1/1/1/1/1/1/1
[0 Intel(R) Arc(tm) B580 Graphics (BMG G21)]  fp16-cm=8x16x16  int8-cm=8x16x32  bf16-cm=8x16x16  fp8-cm=0
[1 llvmpipe (LLVM 20.1.8, 256 bits)]  queueC=0[1]  queueT=0[1]
[1 llvmpipe (LLVM 20.1.8, 256 bits)]  fp16-p/s/u/a=1/1/1/1  int8-p/s/u/a=1/1/1/1  bf16-p/s=1/0
[1 llvmpipe (LLVM 20.1.8, 256 bits)]  subgroup=8(8~8)  ops=1/1/1/1/1/1/1/1/1/1
[1 llvmpipe (LLVM 20.1.8, 256 bits)]  fp16-cm=0  int8-cm=0  bf16-cm=0  fp8-cm=0
loop_count = 4
num_threads = 1
powersave = 0
gpu_device = 0
cooling_down = 1
          squeezenet  min =    2.44  max =    2.51  avg =    2.46
           mobilenet  min =    2.08  max =    2.17  avg =    2.13
        mobilenet_v2  min =    3.18  max =    3.22  avg =    3.20
        mobilenet_v3  min =    3.15  max =    3.30  avg =    3.25
          shufflenet  min =    2.12  max =    2.29  avg =    2.18
       shufflenet_v2  min =    3.61  max =    3.66  avg =    3.64
             mnasnet  min =    3.10  max =    3.18  avg =    3.13
     proxylessnasnet  min =    3.19  max =    3.26  avg =    3.23
     efficientnet_b0  min =    4.79  max =    4.92  avg =    4.84
   efficientnetv2_b0  min =   18.83  max =   18.90  avg =   18.87
        regnety_400m  min =    3.99  max =    4.05  avg =    4.00
           blazeface  min =    1.47  max =    1.53  avg =    1.50
           googlenet  min =    7.19  max =    7.33  avg =    7.25
            resnet18  min =    4.13  max =    4.60  avg =    4.41
             alexnet  min =    2.30  max =    2.42  avg =    2.36
               vgg16  min =    4.34  max =    4.65  avg =    4.51
            resnet50  min =    4.51  max =    4.65  avg =    4.58
      squeezenet_ssd  min =    8.28  max =    8.35  avg =    8.31
       mobilenet_ssd  min =    5.99  max =    6.20  avg =    6.11
      mobilenet_yolo  min =    5.29  max =    5.46  avg =    5.35
  mobilenetv2_yolov3  min =    7.46  max =    7.67  avg =    7.59
         yolov4-tiny  min =   13.22  max =   13.34  avg =   13.27
           nanodet_m  min =    6.67  max =    6.88  avg =    6.79
    yolo-fastest-1.1  min =    2.92  max =    3.14  avg =    3.00
      yolo-fastestv2  min =    3.23  max =    3.46  avg =    3.36
  vision_transformer  min =   26.89  max =   28.45  avg =   27.35
          FastestDet  min =    3.13  max =    3.24  avg =    3.18
```

## License

CC BY 4.0 (Creative Commons Attribution 4.0 International)

## Acknowledgements

Special thanks to the anonymous contributor who provided the Intel Arc B580 for this study.
