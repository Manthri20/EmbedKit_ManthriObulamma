# EmbedKit_ManthriObulamma

## Name
Manthri Obulamma

## Description
This project implements a Ring Buffer (Circular Buffer) in C for the Embedded Developer Fresher Assessment. The ring buffer supports efficient FIFO (First-In-First-Out) data storage and retrieval using a fixed-size buffer of 8 bytes.

## Features

- Buffer initialization
- Write one byte to the buffer
- Read one byte from the buffer
- Check if buffer is full
- Check if buffer is empty
- Get current number of stored bytes
- Prevent overwrite when buffer is full
- Prevent invalid reads when buffer is empty
- FIFO data handling
- Efficient wrap-around using bitwise AND operation

## Build Instructions

Compile the program using:

```bash
gcc -Wall -std=c99 ringbuf.c -o ringbuf
```

## Run

Execute the program using:

```bash
./ringbuf
```

## Module Details

The Ring Buffer is implemented using:

- `uint8_t` for data storage
- Fixed buffer size of 8 bytes
- Head index for write operations
- Tail index for read operations
- Count variable for tracking stored bytes

The implementation uses:

```c
(head + 1) & (BUFFER_SIZE - 1)
```

instead of:

```c
(head + 1) % BUFFER_SIZE
```

This optimization is faster on microcontrollers without a hardware divider and works because the buffer size (8) is a power of two.

## Expected Functionality

1. Write 8 bytes into the buffer.
2. Confirm buffer becomes full.
3. Reject additional writes when full.
4. Read 3 bytes from the buffer.
5. Write 3 new bytes into freed locations.
6. Read all remaining bytes.
7. Confirm buffer becomes empty.
8. Reject reads when empty.

## Files

- `ringbuf.c` - Ring Buffer implementation and demonstration program.
- `README.md` - Project documentation.

