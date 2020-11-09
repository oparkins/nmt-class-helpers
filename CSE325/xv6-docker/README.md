# Setting Up Docker #

One way to run this docker container is to run:

docker run -it --mount src="<where you want you kernel on your local copmuter>",target="/xv6-public/",type=bind --name xv6 xv6


Then to use gdb and such, type:

docker exec -it xv6 gdb

This will open gdb in the container at the same time as the container is running (but you must be running make qemu-nox-gdb)


## Debugging you xv6 project

To use gdb properly, first start `gdb`. Then:

```
target remote <address:port>
file kernel
```

And then you will be ready to go. You can set break points like:
```
b proc.c:556
```

