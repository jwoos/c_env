# Env

## Build
```
make
```

## Notes
- The program will not `fork` before `exec`ing to match functionality of `env` from GNU coreutils 8.29  
Tested by running `env sh -c 'while true; do sleep 5; echo hi;done'` and then `ps -fu` to examine whether it had spawned a child process or not (it hadn't).

- The program will read the environment variables left to right, meaning the rightmost one has the highest precedence.  
```
$ env A=a A=b sh -c 'echo $A'
b
```
