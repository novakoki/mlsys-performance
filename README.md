In this repo, I am going to recap what I learned about optimizing performance in my previous work, especially for machine learning systems. And I also want to introduce some newest techniques on accelerating LLMs. On this page, I am going to introduce some basic concepts and methods on performance engineering. 

## Basic Workflow
1. Measure the performance of Program A
2. Calculate the theoretical peek performance of Program A with current input and hardware
3. Profile Program A
4. Think about possible changes and how much they would theoretically improve the performance
5. Make a change to Program A to produce a hopefully faster Program A*
6. Measure the performance of Program A*
7. Compare the output of A* to that of A
8. If A* get the same output as that of A and is faster than A, set A = A*
9. If A is still not fast enough, go to Step 3

## Measure and Profiling
The "performance" here specifically refers to the latency and throughput of a program. I will not cover other metrics like QPS.


## Theoretical Performance
We all know a modern computer at least has a CPU, a main memory and some I/O devices such as disk, network, screen or keyboard. A typical lifetime of a program would be like below:
1. our programs and data are loaded from I/O devices to the main memory.
2. Then the instructions and data will be read by CPU then executed and the results will be stored to the memory.
3. The results will be eventually written from the memory to I/O devices.

### Roofline Model
## The Ways to Optimization
If we want our programs run faster, what can we do ? Let me get straight, there are only three ways:
1. Reducing computing requirements
2. Add or upgrade hardware
3. Maximize the utility of hardware

### Reducing computing requirements
The fastest program is to do nothing. We can see several different methods in this area, including lossless and lossy methods.
#### Less Work (Improving Algorithm Complexity)
This is the actually the hardest way because usually only computer scientists invent new algorithms which improve something dramatically. But in practice, we just need to know for a specific problem, what is the best algorithm to solve it. Familiar right ? All leetcode problems are training you this capability. In most cases, we only have to come up with a sub-optimal algorithm first just not to be too stupid. Improving algorithm complexity really matters especially on a large input. For example, if we have a N=1,000,000 size input, then we replace the current O(N^2) algorithm with a O(N * log(N)) one, the program should be cost only 1/50000 time of the previous one.

Usually faster algorithms give us the exactly same result as slower ones which means they are lossless algorithms. But sometimes we can only find approximate algorithm, which means we can accept losing a bit accuracy but saving a lot of time. These algorithms are lossy, such as JPEG for image and H.265 for video. However, sometimes we can not get a faster but also good enough algorithm. For example, a lot of Attention or Transformer variances improve the Attention complexity from O(n^2) to O(n) but not get a similar model performance to the original Attention.
#### Less Bits (Quantization)

### Add Or Upgrade Hardware
#### Advanced Hardware (Although Moore's Law Is Dead)
#### More Specific Chips (Heterogeneous Computing)
#### More Computers (Distributed Computing)

### Maximize the utility of hardware
#### All of Memory (Cache)
#### All of CPU (Multicore)
#### Less Waiting (Asynchronous and Pipeline)
