<h1>program to solve producer-consumer problem using Semaphores</h1>
<h1>Source Code</h1>

<h1>Source Code for Seamphore intialization</h1>
```c
#include <stdio.h>
#include <stdlib.h>
#include <sys/ipc.h>
#include <sys/sem.h>

int main() {
    key_t sem_key = ftok("semfile", 75);
    int sem_id = semget(sem_key, 2, 0666 | IPC_CREAT);

    // Set initial values: empty = BUFFER_SIZE, full = 0
    semctl(sem_id, 0, SETVAL, 5); // empty semaphore
    semctl(sem_id, 1, SETVAL, 0); // full semaphore

    printf("Semaphores initialized successfully.\n");
    return 0;
}
```
<h1>Source Code for consumers</h1>
