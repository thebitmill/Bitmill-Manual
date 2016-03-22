# Web Workers API

The web workers API brings multi-threading to the web. Modern CPUs are
comprised of a processor cluster, usually 4-8 cores in one. One core can only
run one "thread" which is analogous to a string of instructions, executed one
by one and in succession. Many tasks that a computer preforms can be divided
such that they can be delegated to multiple processing facilities (in our case
cores) and those facilities can do their work without knowing anything about
what the other cores/processors are doing. This is called having a
paralellizable problem, and is the arena where web workers shine. Many, if not
most, computationally heavy problems are paralellizable which makes web workers
ideal for more advanced web games and applications such as 3D animation, video
processing, image manipulation and so on.

+ <http://www.html5rocks.com/en/tutorials/workers/basics/>
