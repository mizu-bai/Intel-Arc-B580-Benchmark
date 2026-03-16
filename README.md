# Intel Arc B580 Benchmark

- Author: mizu-bai
- Date: Mar 16, 2026

## Environment

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

## Driver Installation

See [Intel(R) Arc(TM) Graphics Driver - Ubuntu*](https://www.intel.com/content/www/us/en/download/747008/intel-arc-graphics-driver-ubuntu.html)

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

### LAMMPS
