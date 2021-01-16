# code-injection

you will use your buffer overflow exploits to inject code into the web server. The goal of the injected code will be to unlink (remove) a sensitive file on the server, namely /home/student/grades.txt. Use zookd-exstack, since it has an executable stack that makes it easier to inject code. The zookws web server should be started as follows.

1. Adapt the shellcode.S to un_link a dedicated file.
2. inject the code in the buffer and execution stack.
3. overwrite the saved rip in the frame to injection code.

# Run the serve with exstack
./clean-env.sh ./zookd-exstack 8080 
