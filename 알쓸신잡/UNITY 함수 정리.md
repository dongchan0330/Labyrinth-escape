# 1. 이벤트 함수 실행 순서
![image](https://angliss.cc/wp-content/uploads/2021/08/132.png)

# 2. 이벤트 함수 종류
    ## 1) void start()
        * 컴포넌트 초기화 부분
        * 스크립트가 붙은 해당 오브젝트가 처음으로 생성되는 순간 혹은 오브젝트 활성화 일 때 최초 1회 실행
    
    ## 2) void Awake()
        * start() 함수보다 먼지 실행되는 시작 함수로 최초 1회 실행
        * start 함수보다 더 빨리 실행해야하는 경우 Awake 사용
    
    ## 3) void Update()
        * 1초에 수십번씩 자신의 상태를 갱신하고 주기적으로 실행
        * 매 프레임마다 실행
    
    ## 4) void FixedUpdate()
        * Update()처럼 반복적으로 실행되나 프레임에 기반하지 않고 어떤 고정적이고 동일한 시간에 기반하여 실행
        * 물리 처리 기능은 FixedUpdate()에서 사용해야 함
    
    ## 5) void LateUpdate()
        * 매 프레임마다 실행되지만 Update()함수보다 늦게 실행
        ex) Update()함수에 캐릭터 이동 방향 계산, LateUpdate()함수에 카메라를 구현해 카메라가 캐릭터를 따라가는 방식으로 구현 가능
    
    ## 6) void OnTriggerEnter(Collider other)
        * Trigger가 체크되어 있는 Collider와 충돌할 경우 자동 실행
        * 주로 충돌 판정 때 많이 사용
        * OnTriggerEnter()함수가 발생하기 위한 조건
            * 두 오브젝트 중 하나 이상은 RigidBody, Collider 컴포넌트를 가지고 있어야 함.
            * IsTrigger 가 둘 중 하나 이상은 활성화해야 함.
        * 그 외 함수
        |이름|설명|
        |:---:|:---:|
        |OnTriggerExit()|Collider와 충돌이 끝난 순간에 작동|
        |OnTriggerStay()|Colloder와 충돌하는 동안에 작동|
    
    ## 7) void OnCollisionEnter(Collision other)
        * Trigger가 체크되지 않은 Collider와 충돌한 경우 자동 실행
        * OnCollisionEnter()함수가 발생하기 위한 조건
            * 두 오브젝트 중 하나 이상은 RigidBody 컴포넌트를 가지고 있어야 함. - IsKinematic은 비활성롸
            * 두 오브젝트가 Collider 컴포넌트를 가지고 있어야 함. - IsTrigger는 비활성화
        * Collider와 Collision의 차이
        |:---:|:---:|
        |Collision|부딪친 오브젝트의 Transform, Collider, GameObject, RigidBody, 속도의 정보감 담겨져 있다.|
        |Collider|물리적인 정보는 담고 있지 않아 Collision보다 담고 있는 정보가 적다|
    
    ## 8) void OnEnable()
        * 스크립트 혹은 스크립트가 붙어있는 오브젝트가 활성화 될 때 마다 자동 실행
        * 컴포넌트가 꺼졌다가 켜질 때마다 1회씩 실행
        * OnEnable()과 start()와의 차이점
        |:---:|:---:|
        |start()|오브젝트가 최초 생성될 때 실행|
        |OnEnable()|오브젝트가 활성화될 때 마다 실행
            

## 참고자료
* <https://ansohxxn.github.io/unitydocs/eventmethod/>