This challenge gave us a file chall.out

This was a ELF 32-bit executable

We could open this in Ghidra to decompile it

Using the decompiler we could see the code

Here we can cheat and see the flag before it is printed out (sort of)

We can see on line 12 there is puts("0xL4ugh&amp;&num;123&semi;Ourfirsteventenjoy&amp;&num;125&semi;");

Translate the weird &amp bits to ascii and we have 0xL4ugh{Ourfirsteventenjoy}

Alternatively, we can do what we think is the intended solution.

If we open the file in gdb we can see in the vuln function it compares eax to 0x64 at 0x080491cf

We can also see this when we open the file in ghidra at line 11 "if(hitme == 100)"

If we put a breakpoint before this point and set eax to 0x64 (100) we can make this comparison correct and get the flag printed out

Regardless, we still need to format the flag to be readable and meet the flag specifications.

However we reach it the flag is:

0xL4ugh{Ourfirsteventenjoy}
