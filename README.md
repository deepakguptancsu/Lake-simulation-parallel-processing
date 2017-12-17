# Lake simulation parallel processing

The code simulates the waves formed in a lake when pebbles are thrown with some given intensity. The code is implemented in 4 separate ways:
- Serial version of the code implemented in C. It is intended to run on a single processor as a single process.
- Implementation in C using CUDA and MPI: The code distributes the computation between processor cores present on different nodes and GPGPUs.
- Implementation in C using openMP and openACC 
- Tensor Flow implementation

Analysis: Input is lake of size 2048*2048 pixels
•	Serial code took 2091.62 seconds when ran on a single processor
•	Only openMP version took 115.13 sec to run on 16 processors (therefore a speedup of 18.17).
•	While only openAcc version took 39.02 sec to run on 1 processor and 1 GPU (therefore a speedup of 53.6).
•	The code parallelized by using both openMP and openAcc when ran on 1 node with 16 processors and 1 GPU took 19.98 sec, i.e. a        speedup of 104.69.
•	Tensor flow version took 7.14 sec to simulate lake on GPU v3.0 i.e. a speed up of 292.94 was achieved
