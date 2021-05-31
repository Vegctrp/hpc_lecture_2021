# Last report of HPC 2021
student number: **21M31298**

## my program(matmul.cpp)
I used MPI(default), SIMD cache blocking, and OpenMP.

change `N=256,1024,2048`
```
cd hpc2021/16_final_report/
module load intel-mpi/19.9.304 gcc/10.2.0
mpicxx matmul.cpp -march=native -O3 -fopenmp
mpirun -np 32 ./a.out
```

### results
```
N    : 256
comp : 0.000429 s
comm : 0.249239 s
total: 0.249668 s (0.134396 GFlops)
error: 0.000016
```

```
N    : 1024
comp : 0.008125 s
comm : 0.311686 s
total: 0.319811 s (6.714855 GFlops)
error: 0.000102
```

```
N    : 2048
comp : 0.093111 s
comm : 0.305135 s
total: 0.398247 s (43.138739 GFlops)
error: 0.000258
```

## default (example.cpp)
change `N=256,1024`
```
cd hpc2021/16_final_report/
module load intel-mpi/19.9.304 gcc/10.2.0
mpicxx example.cpp -O3 -fopenmp
mpirun -np 32 ./a.out
```
 
### results
```
N    : 256
comp : 0.000902 s
comm : 0.316702 s
total: 0.317604 s (0.105648 GFlops)
error: 0.000016
```

```
N    : 1024
comp : 0.198284 s
comm : 0.251931 s
total: 0.450215 s (4.769909 GFlops)
error: 0.000129
```