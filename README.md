# thread-safe-counter
![시간](https://user-images.githubusercontent.com/81306023/121806312-4596dc80-cc8a-11eb-8e3f-6cd6d302f1c2.JPG)


# analysis
A mutex simply blocks access to the critical section through the 
```sh
pthread_mutex_init(&c->lock, NULL);
```
command.
These commands always put the cpu on standby for faster processing.

However, in the case of a semaphore, it must be implemented so that as many threads as the value of the set variable can access it.
To put it simply, a mutex has 1 key per room,
A semaphore should be designed to have multiple identical locks in multiple rooms.

To implement such a semaphore, a complex design is required.

Even if you look at the code right away, it was necessary to code using int type variables to switch between 1 and 0.
Because of this design, semaphores, unlike mutexes, cause differences in the instruction executed, which in turn causes differences in execution speed.

# environment
OS Version : WSL2
```sh
command
gcc semaphore.c -lpthread
time ./a.out
```
