# OpenMP_1
Parallelize the FOR loop that iterates over the pixel rows in the fractal code (and not the FOR loop over the frames as in the previous projects).



1. Base your code on the serial code from Project 1.
2. Make the code print “OpenMP” instead of “serial”.
3. Do not include any new header files.
4. Do not change the delta computation.
5. Only parallelize the for-row loop using a “parallel for” pragma.
6. Use “default(none)” and list all shared and private variables (excluding constants and variables
   that have not yet been declared).
7. Do not use “num_threads(…)”.
8. Use “schedule(SCHED)” as the schedule, where “SCHED” will be specified during compilation.
9. Verify, on small inputs, that the correct fractal is computed.



On the machines in the parallel lab, compile your OpenMP code as follows:
g++ -march=native -O3 -fopenmp fractal_omp.cpp -o fractal_cyc -DSCHED="static,1"
g++ -march=native -O3 -fopenmp fractal_omp.cpp -o fractal_dyn -DSCHED="dynamic,1"
g++ -march=native -O3 -fopenmp fractal_omp.cpp -o fractal_gui -DSCHED="guided,1"
On Stampede, compile your OpenMP code as follows:
icc -xhost -O3 -openmp fractal_omp.cpp -o fractal_cyc -DSCHED="static,1"
icc -xhost -O3 -openmp fractal_omp.cpp -o fractal_dyn -DSCHED="dynamic,1"
icc -xhost -O3 -openmp fractal_omp.cpp -o fractal_gui -DSCHED="guided,1"
2

Run the code using the submission script at /home1/00976/burtsche/Parallel/fractal_omp.sub. Do
not modify this script
.
Question 4.1a) What runtimes do you get (in seconds)? Present the runtimes in a table for the
cyclic, dynamic, and guided schedules from left to right and “increasing” problem sizes from top
to bottom. Use three digits after the decimal point.

Question 4.1b) Why are dynamic and guided substantially faster than the cyclic schedule?

Question 4.1c) Why is this code significantly slower than the pthread code from the previous project?
Name the source file “fractal_omp.cpp” and submit it on TRACS.



