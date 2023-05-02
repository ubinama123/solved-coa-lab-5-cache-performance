Download Link: https://assignmentchef.com/product/solved-coa-lab-5-cache-performance
<br>
Cache Performance can be improved by two techniques: reducing the miss rate or reducing the miss penalty. Lab 4 (Cache Simulator) focuses on reducing the miss rate by reducing the probability that two different memory blocks will contend for the same cache location. In this lab, cache performance is going to be improved by reducing the miss penalty, and further measured by considering program execution cycles and memory stall cycles. You should simulate both CPU and cache behaviors with C/C++ style simulators with given timing assumptions. This Lab will help you understand the impact of cache performance.

2.       Requirement

<ul>

 <li>Please attach your names and student IDs as comment at the top of each file.</li>

 <li>Please modify your “direct_mapped_cache_lru.cpp” in Lab 4 to complete this Lab, and provide Makefile to compile your source codes into executable file named <strong>simulate_caches</strong>.</li>

 <li>You are asked to simulate the single-cycle CPU and cache behaviors of a function for matrix multiplication: <em>matmul</em>(<em>A</em>, <em>B</em>), where both <em>A</em> and <em>B</em> are matrices with their dimensions to be <em>m</em> × <em>n</em> and <em>n</em> × <em>p</em>, respectively. The assembly code of <em>matmul</em>(<em>A</em>, <em>B</em>) is given as matmul.txt. According to matmul.txt and following delay assumptions, you can calculate and analyze the performance.</li>

</ul>

For example, considering the memory organization shown in Fig 1(c), if there is a miss in both L1 and L2, a 32-word block will be transferred from memory to L2, a 4-word block will be transferred from L2 to L1, and the required data will be sent to CPU with 1+32×(1+100+1+10)+4×(1+10+1+1)+1+1 = 3639 memory stall cycles.

3.       Input/output

The first line contains three hexadecimal numbers <em>ADDR</em><sub>0</sub>, <em>ADDR</em><sub>1</sub>, and <em>ADDR</em><sub>2</sub>, which indicate the base addresses of input matrices <em>A</em>, <em>B</em> and output matrix <em>C</em>, and three decimal integers, <em>m</em>, <em>n</em>, and <em>p</em> (<em>m</em>, <em>n</em>, <em>p</em> are 2<em><sup>x</sup></em>, 2 ≦ <em>x </em>≦ 10), which indicate the dimensions of matrices <em>A<sub>m</sub></em>×<em><sub>n</sub></em> and <em>B<sub>n</sub></em>×<em><sub>p</sub></em>, respectively. In the following <em>m</em>+<em>n</em> lines are the elements of matrices <em>A</em> and <em>B</em>. Your output should contain the result matrix <em>C<sub>m </sub></em>×<em><sub>p</sub></em> and the simulated program execution cycles and the total memory stall cycles according to the calculation of miss penalty in p.33-34 of Chapter 5 slides.

4.       Report

Briefly write down how you calculate the memory stall cycles of different miss condition. Based on the results of CPU and cache simulation, compare and discuss the difference among the three memory organizations described in Fig 1.

5.       Bonus: Performance improvement by software

The processor performance can be further improved by software, i.e., compiler. To get the bonus, you should rewrite the assembly code of <em>matmul</em>(<em>A</em>, <em>B</em>) as <strong>bonus_matmul.txt</strong> and calculate the new memory stall cycles with your C/C++ style simulator. The reasons why your <em>matmul</em>(<em>A</em>, <em>B</em>) is faster than the original one should be written down in the report. Note that the functionality of your assembly code should be the same as the original one, i.e., it should calculate the correct matrix multiplication result <em>C<sub>m</sub></em>×<em><sub>p</sub></em>, which would be verified by TA’s simple MIPS assembler (only includes <strong>addi</strong>, <strong>addu</strong>, <strong>subu</strong>, <strong>mul</strong>, <strong>slt</strong>, <strong>beq</strong>, <strong>bne</strong>, <strong>j</strong>, <strong>lw</strong>, <strong>sw</strong>, see bonus_readme.txt for details) and single-cycle CPU. Besides, every instruction has its delay penalty and the total delay should be recalculated and written into the report!