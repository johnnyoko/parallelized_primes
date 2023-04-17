# Abstract
The aim of this project is to explore the computation of prime numbers, a fundamental topic in mathematics that has been of great interest to mathematicians throughout history. The motivation behind this research is to discover a faster way to find prime numbers computationally, or to uncover new prime numbers. While all numbers under $2^{110000000}-1$ have been checked using Lucas-Lehmer Primality Testing, verifying these numbers manually is not feasible due to their immense size, making the problem computationally expensive. To address this challenge, the study focuses on the use of parallel computing to increase the speed of prime number discovery. The research examines the Great Internet Mersenne Prime Search (GIMPS) software and aims to benchmark the optimization of parallel computing methods. Due to the restriction of modifying the GIMPS code, I wrote a program to find prime numbers and ran it in parallel to evaluate the speed increase. The program will mainly run on a 2019 Macbook Pro with 2.3 GHz 8-Core Intel Core i9, Intel UHD Graphics 630 1536 MB, and 32 GB 2667 MHz DDR4. The successful outcome of this study would be to reduce the time it takes to check for prime numbers through parallel computing optimization.

# Benchmarking
This code implements a benchmark for finding Mersenne primes using the Lucas-Lehmer test. Mersenne primes are prime numbers that are one less than a power of two, i.e., numbers of the form $2^p - 1$ where p is a prime number. The Lucas-Lehmer test is an efficient method for determining whether a given value of p produces a Mersenne prime.


# Functions
The lucas_lehmer function implements the Lucas-Lehmer test. It takes an integer p as input, and returns True if $2^p - 1$ is a Mersenne prime, and False otherwise. The function computes a sequence of numbers using a recurrence relation, and checks whether the last number in the sequence is equal to 0 modulo $2^p - 1$.

The find_mersenne_primes function takes an integer max_p as input, and finds all Mersenne primes up to $2^{max\_p} - 1$ using the Lucas-Lehmer test. It does this by iterating over all prime numbers less than max_p, and checking whether each one produces a Mersenne prime using the lucas_lehmer function. The function returns a list of Mersenne primes that were found, as well as the total time taken to perform the computation.

The optimized find_mersenne_primes() function takes two parameters: max_p, which is the maximum prime exponent to test for a Mersenne prime, and num_processes, which is the number of processes to use for parallelization. In the current example, it is finding Mersenne primes up to 2000 using 16 processes.
# Conclusion
Based on the implementation of the Lucas-Lehmer test with parallel processing, we expect that the output of our program will show a significant decrease in the time taken to calculate Mersenne primes as the number of cores used increases. By distributing the computation of Mersenne primes across multiple cores using the multiprocess module, we can take advantage of the parallel computing capabilities of modern CPUs and reduce the overall computation time. The output of our program, which can be found in our GitHub repository, will demonstrate the effectiveness of parallel processing in reducing the time required to calculate Mersenne primes.

# References
Lucas-Lehmer test: https://en.wikipedia.org/wiki/Lucas%E2%80%93Lehmer_primality_test

Multiprocessing in Python: https://docs.python.org/3/library/multiprocessing.html

Time module in Python: https://docs.python.org/3/library/time.html

Matplotlib library for Python: https://matplotlib.org/

NumPy library for Python: https://numpy.org/

Seaborn library for Python: https://seaborn.pydata.org/

Pandas library for Python: https://pandas.pydata.org/
