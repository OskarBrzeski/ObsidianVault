# Usage
Basic Example
```c
#include "raylib.h"

int
main(void)
{
	InitWindow(800, 600, "3D Renderer");

	while (!WindowShouldClose())
	{
		BeginDrawing();
		ClearBackground(BLACK);
		DrawFPS(8, 8);
		EndDrawing();
	}

	CloseWindow();

	return 0;
}
```