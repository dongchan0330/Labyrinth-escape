## 1) 캐릭터 이동 
  * 캐릭터를 이동시키기 위해 방향키를 입력해 이동하도록 해야 한다. 
  * 유니티 기능 중 입력관리자를 통해 구현
  * 캐릭터 이동 벡터는 x, z축만 사용
  * normalize를 이용해 대각선 이동

```c#
float hAxis = Input.GetAxisRaw("Horizontal");
float vAxis = Input.GetAxisRaw("Vertical");
Vector3 moveVec = new Vector3(hAxis, 0, vAxis).normalized; 
```
<img src = "./image/input manager.png" height = "500" width = "600"></img><br/>

## 2) 캐릭터 점프
  * 캐릭터가 점프를 하기 위해 위와 같은 방법으로 입력관리자를 통해 입력받을 수 있도록 구현

  ```c#
  public float jumpPower;
  bool jDown = Input.GetButtonDown("Jump");
  void jump(){
    if(jDown){
        rigid.AddForce(Vector3.up * jumpPower, ForceMode.Impulse);
        anim.SetBool("isJump", true);
        anim.SetTrigger("doJump");
    }
  }
  ```
  * rigidBody 기능 중 AddForce를 사용해 점프 구현
  * AddForce: RigidBody에 힘을 전달해 주는 기능
  * AddForce 힘의 종류
  
  |이름|설명|
  |:---:|:---:|
  |Force| 해당 리지드바디(rigidbody)의 질량을 사용해서, 연속적인 힘(force)을 가하는 경우에 사용합니다.|
  |Acceleration|질량을 무시하고, 리지드바디에(rigidbody)에 연속적인 가속력(Acceleration)을 가합니다.|
  |Impulse|	리지드바디의 질량을 사용해서, 짧은 순간의 힘을 가하는 경우에 사용합니다.|
  |VelocityChange|질량을 무시하고, 리지드바디(rigidbody)에 속도 변화를 짧은 순간에 적용할 경우에 사용합니다.|


  ***
  ## 참고자료
  * [유튜브 골든메탈 채널](https://www.youtube.com/c/GoldMetal)
  * <https://allaboutmakers.tistory.com/24>
