Process is just an instance of program. Program contains set of instructions
that it want cpu to execute. CPU at a time can execute only one instruction.
It switches between processes to support multitasking. Program instructions are
loaded in RAM. CPU reads the instruction from RAM.

If a process can be split up in chunks so that execution of one chunk doesn't
affect the execution of other. We can execute those chunks in paralell and use
the results got from chunk to combine everything. Chunk can be referred as
Threads. A Thread uses the resources of 'its process'
