# RC_4th_Standard
(주) 소프트스퀘어드 의 부트캠프인 '라이징캠프' 4주차 미션 과제입니다.

아이폰 메모장 어플 클론입니다.

## 핵심개념

📕 RecyclerView 는 ListView와 동일하지만, 내부 아이템 틀을 재사용할 수 있으므로 메모리 절약에 용이하다.

## 진행상황

🚂 메모 화면들(메모 목록, 작성화면) 간의 화면전환들을 Intent로 처리했다.

→ 상황에 따라 (읽기, 작성, 수정, 저장) Boolean 변수를 생성해서 각 상황에 맞게 동작하도록 작성했다.

→ ~~불의의 사고가 일어났다..~~ 미뤄진 김에 지저분해보였던 코드를 리빌딩하기로 결정했다. (챌린지는 자연스럽게 미뤄졌다..)

→ MainActivity에는 하단바와 상단바만 작성 후 FrameLayout을 사용해서 Fragment들(메모 화면들) 을 교체해주는 방식으로 변경했다.

→ 위의 Boolean상황변수들, 오고 갈 데이터들은 LiveData로 처리했다.

~~(그래도 아직 여전히 코드는 지저분하더라..)~~

## 에러사항

💢 ViewModel 사용시, MutableList 형식 LiveData의 Value값에 바로 메모 목록 아이템을 .add()로 추가했더니 추가되지 않았다!

💢 스탠다드 미션 원본에서는 Dialog에서 화면 전체를 캡쳐하듯이 작게 보여주는 이미지가 있으나, 내 머리로는 화면을 캡쳐 후 띄워주는 방식밖에 생각나지 않아서 결국 검은 화면으로 처리했다..

💢 RecyclerView 체크박스 유지 미션에서 언제 바뀐 Boolean 값을 RV어댑터에 넣어줘야 할까 고민이었다..

→ ~~결국 또~~ LiveData를 사용하여 바뀌는 즉시 적용되도록 설정했다..

## 피드백

🤦🏻 ViewModel에 LiveData가 아닌 일반 MutableList 변수를 추가 후, setValue() 를 사용하여 해결했다!

→ 항상 LiveData는 변수만 사용해서 몰랐는데, 배열 같은 경우는 setValue() 를 사용해야 한다고 한다.


![Screenshot_20220120-230107_RC_Standard_4](https://user-images.githubusercontent.com/80454599/163403249-236a8aed-8bb7-48eb-aad6-9d78c73b3744.jpg)
![Screenshot_20220120-230123_RC_Standard_4](https://user-images.githubusercontent.com/80454599/163403257-218c5b03-01ff-4a32-aa77-b3c0bcb657ff.jpg)

