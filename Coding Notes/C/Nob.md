C header-library by Tsoding to build C projects without outside dependencies.
https://github.com/tsoding/nob.h
# Usage
Include the `nob.h` file in the project directory.

Create a file called `nob.c` and include the following:
```c
#define NOB_IMPLEMENTATION
#define BUILD_FOLDER "./build/"
#define SRC_FOLDER   "./src/"
#include "nob.h"

int
main(int argc, char** argv)
{
	NOB_GO_REBUILD_URSELF(argc, argv);
	if (!mkdir_if_not_exists(BUILD_FOLDER)) return 1;

	Cmd cmd = {0};
	cmd_append(&cmd, "cc");
	cmd_append(&cmd, "-Wall", "-Wextra", "-Werror", "-Wpedantic");
	cmd_append(&cmd, "-o", BUILD_FOLDER "main", SRC_FOLDER "main.c");
	cmd_append(&cmd, "-I" LIBS_FOLDER);
	cmd_append(&cmd, "-L" LIBS_FOLDER);
	cmd_append(&cmd, -lm");

	if (!cmd_run(&cmd)) return 1;

	return 0;
}

```
Compile this file.
```bash
gcc -o nob nob.c
```
Now run the file to compile your project.
```bash
./nob
```
Nob will automatically rebuild itself if it detects changes to `nob.c`, so you can keep calling the executable to compile the project.