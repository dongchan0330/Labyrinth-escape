1. 캐릭터 이동 구현
  * 캐릭터를 이동시키기 위해 방향키를 입력해 이동하도록 해야 한다. 
  * 유니티 기능 중 입력관리자를 통해 구현
  * 캐릭터 이동 벡터는 x, z축만 사용
  * normalize를 이용해 대각선 이동

```c#
float hAxis = Input.GetAxisRaw("Horizontal");
float vAxis = Input.GetAxisRaw("Vertical");
Vector3 moveVec = new Vector3(hAxis, 0, vAxis).normalized; 
```
<img  align = "left" src = "./image/input manager.png" height = "500" width = "600">
