1. 캐릭터 이동 구현
* 캐릭터를 이동시키기 위해 방향키를 입력해 이동하도록 해야 한다.

```c#
float hAxis = Input.GetAxisRaw("Horizontal");
float vAxis = Input.GetAxisRaw("Vertical");
```
![image]("input manager.png")