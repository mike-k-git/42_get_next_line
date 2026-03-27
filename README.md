_This project has been created as part of the 42 curriculum by mkugan._

# GET_NEXT_LINE

This project implements the `get_next_line` function in C, which reads a line from a file descriptor, handling multiple file descriptors and buffer management.

## Features
- Reads a line from a file descriptor, including the newline character if present.
- Handles multiple file descriptors simultaneously (bonus version).
- Buffer management and memory handling.
- Custom utility functions for string operations and memory management.

## Files
- `get_next_line.c` / `get_next_line.h`: Main implementation and header for the standard version.
- `get_next_line_bonus.c` / `get_next_line_bonus.h`: Bonus version supporting multiple file descriptors.
- `get_next_line_utils.c` / `get_next_line_utils_bonus.c`: Utility functions for both versions.

## Usage
1. **Include the header:**
   ```c
   #include "get_next_line.h"
   // or for bonus
   #include "get_next_line_bonus.h"
   ```
2. **Call the function:**
   ```c
   char *line = get_next_line(fd);
   ```
   - `fd` is the file descriptor to read from.
   - The function returns the next line read, or `NULL` on EOF or error.
3. Stop before the end of a file
   Call `gnl_clear(fd)` to clear any leftover data.

## Notes
- The buffer size can be changed by defining `BUFFER_SIZE` during compilation:
  ```bash
  cc -D BUFFER_SIZE=100 ...
  ```
- The maximum number of file descriptors supported is defined by `FD_MAX` (default: 1024).
