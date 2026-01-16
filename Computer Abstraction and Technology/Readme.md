<details>
<summary>Table of Contents</summary>
<ol>
  <li>
    <a href='#abstraction-in-computer-architecture'>Abstraction in Computer Architecture</a>
  </li>
  <li>
    <a href='#eight-great-ideas'>Eight Great Ideas</a>
  </li>
  <li>
    <a href='#components-of-a-computer'>Components of a Computer</a>
  </li>
  <li>
    <a href='#performance-factors'>Performance Factors</a>
  </li>
</ol>
</details>

## Abstraction in Computer Architecture
<em>Abstraction</em> manages complexity by hiding lower-level details

Key abstraction layers:
<ul>
  <li><em>Instruction Set Architecture (ISA)</em>
    <ul>
      <li>Interface between hardware and software</li>
      <li>Defines instructions, registers, memory model, and input/output behavior</li>
    </ul>
  </li>
  <li>Implementation of an ISA (Microarchitecture)
    <ul>
      <li>The different components like the ALU, registers, etc. the define the ISA in hardware</li>
    </ul>
  </li>
  <li>Implementation Level of the Microarchitecture (RTL)
    <ul>
      <li>How all the components of the microarchitecture are connected</li>
    </ul>
  </li>
</ul>

## Eight Great Ideas
<ol>
  <li>Design for Moore's Law</li>
  <li>Use abstraction to simplify design</li>
  <li>Make the common case fast</li>
  <li>Performance via parallelism</li>
  <li>Performance via pipelining</li>
  <li>Performance via prediction</li>
  <li>Hierarchy of memories</li>
  <li>Dependability via redundancy</li>
</ol>

## Components of a Computer
<ul>
  <li><em>Input/Output</em>
    <ul>
      <li>Display, keyboard, mouse</li>
      <li>Storage devices like hard disks, flashes, CD</li>
      <li>Network adapters</li>
    </ul>
  <li><em>Processor</em>
    <ul>
      <li>Datapath performs operations on data</li>
      <li>Control sequences datapath and memory</li>
      <li>Cache memory
        <ul>
          <li>Small fast SRAM memory for immediate access to data</li>
        </ul>
      </li>
    </ul>
  </li>
</ul>

## Performance Factors
<ul>
  <li><em>Algorithm</em> determines the number of operations executed</li>
  <li><em>Programming language, compiler, architecture</em> determine the number of machine instructions executed per operation</li>
  <li><em>Processor and memory system</em> determine how fast instructions are executed</li>
  <li><em>I/O System</em> determines how fast input/output operations are executed</li>

### Defining Performance
There are two main metrics:
<ul>
  <li><em>Response time</em> is the time to complete a task</li>
  <li><em>Throughput</em> is the number of tasks completed per unit of time</li>
</ul>

Faster CPUs have a better response time and more CPUs have higher throughput

<em>Relative performance</em> is where performance = 1 / execution time

### Measuring Execution Time
<ul>
  <li>Elapsed time is the total response time, including all aspects like processing, input/output, OS overhead, and idle time. This determines system performance</li>
  <li>CPU time is the time spent processing a given job</li>
</ul>

#### CPU Time Formula
CPU time = CPU clock cycles * clock cycle time = CPU clock cycles / clock rate

Performance is improved by:
<ul>
  <li>Reducing number of clock cycles</li>
  <li>Increasing clock rate</li>
</ul>

#### Instruction Count and Clock Cycles per Instruction (CPI)
Clock cycles = instruction count * cycles per institution

CPU time = instruction count * CPI * clock cycle time = (instruction count * CPI) / clock rate