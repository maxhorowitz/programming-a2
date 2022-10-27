TODO: we were thinking this has to do with the priority order of the IF statements
for each of the gates. For the binary semaphore example, the push, pop, and validation
gates' ordering will cause some of the threads to wait longer than the other ones. 
The validate function can be starved a few ways. First, if pop and push keep being 
called and their conditions are valid then they will keep being called before validate(). 
Additionally, we always check pop before validate, and therefore it's very unlikely 
that the stack is full AND have nobody want to pop so that validate's conditions 
are met to open the gate.