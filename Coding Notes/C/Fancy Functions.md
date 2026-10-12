```c
#include <stdio.h>

typedef struct FuncParams {
  int x;
  int y;
  float scale;
} FuncParams;
#define Func(...) _Func((FuncParams){.y = 5, __VA_ARGS__})
void _Func(FuncParams params) {
  printf("%d %d %f\n", params.x, params.y, params.scale);
}

int main() {
  printf("Hello World\n");
  Func(.x = 2, .scale = 3.5);
  return 0;
}
```