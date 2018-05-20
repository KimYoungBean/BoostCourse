# BoostCourse

### [BoostCourse-iOS](http://www.edwith.org/boostcourse-ios)

### 오리엔테이션
- [x] 01. Hello! iOS Developer!
- [x] 02. 개발 이야기
- [x] 03. 코스 시작에 앞서...
- [x] 04. 시작합니다!
- - -
### 1. 음원 재생기 애플리케이션 (18.05.05 완료)
- [x] 0.Hello!
- [x] 1. 시작 그리고 Xcode
- [x] 2. 애플리케이션 만들기
    * 인터페이스 빌더의 객체를 코드와 연결(IBOutlet)
        * 코드로 먼저 IBOutlet을 생성한 후 인터페이스 빌더의 Outlet Inspector를 통해 연결
        * 코드로 먼저 IBOutlet을 생성한 후 인터페이스 빌더에서 View Controller 우클릭 후 팝업에서 연결
        * 인터페이스 빌더에서 코드로 끌어당겨 연결
    * 인터페이스 빌더의 객체에서 발생한 액션을 코드의 메서드와 연결
        * 코드로 먼저 IBAction을 생성한 후 인터페이스 빌더의 Outlet Inspector를 통해 연결
        * 코드로 먼저 IBAction을 생성한 후 인터페이스 빌더에서 View Controller 우클릭 후 팝업에서 연결
        * 인터페이스 빌더에서 코드로 끌어당겨 연결
- [x] 3. Foundation과 UIKit 그리고 Cocoa Touch
- [x] 4. 오토 레이아웃
    * 인터페이스 빌더에서 오토레이아웃 구현하기
        1. 뷰와 뷰 사이에 ctrl 키 누르고 드래그하는 방식
        2. 스택, 정렬, 핀 그리고 리졸브를 사용하는 방식
        3. 인터페이스 빌더가 제약 설정하는 방식
- [x] 5. iOS의 View 체계
- [x] 6. MVC
    * Model-View-Controller
        * Model : 애플리케이션과 관련된 데이터를 캡슐화하고, 해당 데이터를 조작하고 처리하는 로직과 계산을 정의
        * View : 애플리케이션 내에서 사용자가 볼 수 있는 객체
        * Controller : 하나 이상의 애플리케이션 뷰 객체와 하나 이상의 모델 객체 사이의 코디네이터 또는 중개자 역할
- [x] 7. Apple Developer Documentation
    * Doumentation 읽는 연습할 것!
- [x] 8. Summary
- - -
### 2. 회원가입 화면 구현 (18.05.10 완료)
- [x] 0. Hello!
- [x] 1. Human Interface Guidelines
- [x] 2. 화면의 전환
    * Modal : 이목을 집중해야 하는 화면을 다른 화면 위로 띄워(Presenting) 표현하는 방식 (= Android의 Intent, Activity)
        * 뷰 컨트롤러를 화면 상에 나타내는 방법 2가지(컨테이너 뷰 컨트롤러에 임베드, 프레젠테이션)
            * Fuil-Screen Presentaion Style : 화면 전체를 덮으며, 아래의(underlying) 기본 콘텐츠와 상호작용을 방지
            * The Popover Style : 뷰 컨트롤러를 팝오버뷰로 나타냄(iPad만 지원)
            * The Current Context Styles : 아래 뷰 컨트롤러의 콘텐츠 영역에 콘텐츠를 올리는 형태
            * Custom Presentation Styles : 정의한 커스텀 스타일을 사용하여 뷰 컨트롤러를 표시
            * Transition Styles : 뷰 컨트롤러를 표시하는데 사용하는 애니메이션 유형을 결정
- [x] 3. 뷰의 상태변화 감지
    * 뷰의 상태변화 메서드
        * func viewDidLoad()
            - 뷰 계층이 메모리에 로드된 직후 호출되는 메서드
            - 뷰의 추가적인 초기화 작업을 하기 좋은 시점
            - 메모리에 처음 로딩 될때 1회 호출되는 메서드로, 메모리 경고로 뷰가 사라지지 않는 이상 다시 호출되지 않음
            - (= Android의 onCreate() )
        * func viewWillAppear(_ animated: Bool)
            - 뷰가 뷰 계층에 추가되고 화면이 표시되기 직전에 호출되는 메서드
            - 뷰의 추가적인 초기화 작업을 하기 좋은 시점
            - 다른 뷰로 이동했다가 되돌아오면 재호출되는 메서드로, 화면이 나타날때마다 수행해야하는 작업을 하기 좋은 시점
            - (= Android의 onResume() )
        * func viewDidAppear(_ animated: Bool)
            - 뷰가 뷰 계층에 추가되어 화면이 표시되면 호출되는 메서드
            - 뷰를 나타내는 것과 관련된 추가적인 작업을 하기 좋은 시점
            - (= Android의 onStart() )
        * func viewWillDisappear(_ animated: Bool)
            - 뷰가 뷰 계층에서 사라지기 직전에 호출되는 메서드
            - 뷰가 생성된 뒤 발생한 변화를 이전상태로 되돌리기 좋은 시점
            - (= Android의 onPause() )
        * func viewDidDisappear(_ animated: Bool)
            - 뷰가 뷰 계층에서 사라진 후 호출되는 메서드
            - 뷰를 숨기는 것과 관련된 추가적인 작업을 하기 좋은 시점
            - 시간이 오래 걸리는 작업은 하지 않는 것이 좋음
            - (= Android의 onStop() )
    * 레이아웃의 상태변화 메서드
        * func viewWillLayoutSubviews()
            - 뷰가 서브뷰의 레이아웃을 변경하기 직전에 호출되는 메서드
            - 서브뷰의 레이아웃을 변경하기 전에 수행할 작업을 하기 좋은 시점
        * func viewDidLayoutSubviews()
            - 서브뷰의 레이아웃이 변경된 후 호출되는 메서드
            - 서브뷰의 레이아웃을 변경 한 후 추가적인 작업을 수행하기 좋은 시점
    (ps. override 및 super 작성 필요)
- [x] 4. Delegation
    * Delegate : (사전적의미) 위임하다, 선정하다, 대리하다
    * Delegation Design Pattern : 델리게이션 디자인 패턴은 하나의 객체가 다른 객체를 대신해 동작 또는 조정할 수 있는 기능을 제공
    * 델리게이트는 특정 상황에 대리자에게 메시지를 전달하고 그에 적절한 응답 받기 위한 목적으로 사용
    * control + command + click로 jump to definition 가능
    * 데이터소스(Data Source)
    * 프로토콜(Protocol)
    * (= Android의 implement methods)
- [x] 5. Singleton
    * 디자인 패턴 중 하나
    * 특정 클래스의 인스턴스가 오직 하나임을 보장하는 객체 -> 다른 인스턴스들이 공유해서 사용할 수 있음.
    * 객체가 불필요하게 여러 개 만들어질 필요가 없는 경우에 많이 사용. 예를 들면 환경설정, 네트워크 연결처리, 데이터 관리 등
- [x] 6. Target-Action
    * 디자인 패턴 중 하나
    * 객체는 이벤트가 발생할 때 다른 객체에 메시지를 보내는 데 필요한 정보를 포함.
    * 액션은 특정 이벤트가 발생했을 때 호출할 메서드를 의미(@IBAction). 타겟은 액션이 호출될 객체를 의미.(addTarget)
    * 이벤트 발생 시 전송된 메시지를 액션 메시지라고 하고, 타겟은 프레임워크 객체를 포함한 모든 객체가 될 수 있으나, 보통은 컨트롤러.
- [x] 7. Gesture Recognizer
    * 특정 제스처 이벤트가 일어날 때 마다 각 타깃에 맞는 액션 메시지를 보내어 제스처 관련 이벤트를 처리가능
    * UIGestureRecognizer의 하위클래스
        - UITapGestureRecognizer : 싱글탭 또는 멀티탭 제스처
        - UIPinchGestureRecognizer : 핀치(Pinch) 제스처
        - UIRotationGestureRecognizer : 회전 제스처
        - UISwipeGestureRecognizer : 스와이프(swipe) 제스처
        - UIPanGestureRecognizer : 드래그(drag) 제스처
        - UIScreenEdgePanGestureRecognizer : 화면 가장자리 드래그 제스처
        - UILongPressGestureRecognizer : 롱프레스(long-press) 제스처
    * UIGestureRecognizer의 주요 메서드
        - init(target: Any?, action: Selector?) : 제스처 인식기를 타깃-액션의 연결을 통해 초기화
        - func location(in: UIView?) -> CGPoint : 제스처가 발생한 좌표를 반환
        - func addTarget(Any, action: Selector) : 제스처 인식기 객체에 타깃과 액션을 추가
        - func removeTarget(Any?, action: Selector?) : 제스처 인식기 객체로부터 타깃과 액션을 제거
        - func require(toFail: UIGestureRecognizer) : 여러 개의 제스처 인식기를 가지고 있을 때, 제스처 인식기 사이의 의존성을 설정
- [x] 8. Summary
