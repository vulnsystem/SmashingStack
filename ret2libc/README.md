# return-to-libc
To bypass a non-executable stack, you need to first find the code you want to execute. This is often a function in the standard library, called libc, such as execve, system, or unlink. Then, you need to arrange for the stack and registers to be in a state consistent with calling that function with the desired arguments. Finally, you need to arrange for the ret instruction to jump to the function you found in the first step. This attack is often called a return-to-libc attack.

#There are two labs for ret2lib.

1. exploit-ret2libc.py         which use accidentally function in zookd.c as ROP gadget.

2. exploit-ret2lib-wohelper.py which not use accidentally function in zookd.c as ROP gadget. And the gadgets will be found by Ropper

#Run the server:

./clean-env.sh ./zookd-nxstack 8080

#Ropper

Link: https://github.com/sashs/Ropper

Find the gadgets by ropper --file ret2libc --search "% ?di"
