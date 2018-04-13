# 프로그래밍 하다 막힌 부분 기록해두기 (2018.4.12~


프로그래밍은 이렇게 막히는 부분 다시 정리하면서 실력이 느는듯

****

-모든 소프트웨어는 확장과 축소, 생성과 소멸이 자동적으로 이루어지는 게 필요하다고 생각하자

-확장과 축소, 생성과 소멸이 이루어지는 가장 기초는 자료구조임. 따라서 자료구조를 다 구현해볼 필요 있음

-그래야 나만의 라이브러리 개발이 가능해짐


*****

1 문제 빨리 해결하는 팁

-보통 객체들이 동작하려면 컨테이너와 컨테이너에 포함된 객체로 구성되어있다고 생각하자

-포함된 객체 클래스는 VO, DTO처럼 생각하자

-컨테이너 역할클래스도 생성자, getter, setter가 있는데, 여기서의 getter, setter은 주로 컨테이너 자체의 size()

-객체 클래스라면 생성자(보통 이름자체에 강제조건에 대한 힌트가 있음), getter,setter를 생각하자

-조건문인 경우, 반복되는 코드보다 차이나는 코드를 이해해야 핵심 이해 가능




<hr>

<h1> 프런트엔드 <h1>

<h2> API와 JSON </h2>

<h2> Jquery 구조 분석 </h2>


<hr>

<h1> 백엔드 <h1>

<h2> 스프링, 프레임워크 </h2>

디자인패턴과 라이브러리 이용해 MVC 프레임워크 구현하면서 막히는 부분 

-각 클래스의 역할 제대로 이해 필요

<h4>1 프. 컨(디스패처 서블릿)의 역할- (안 어려움)</h4>

-요청 URL에서 서블릿 경로 알아내기

-조건문 사용하여 적절한 페이지 컨트롤러에게 실행 위임 

-요청 매개변수로부터 VO객체 준비

-JSP로 위임

-오류 처리


<h4>2 컨트롤러(일반클래스) - (안 어려움)</h4>

-왜 서블릿이 아니고 일반클래스인가 , 서블릿과의 차이는 무엇인가 (일반클래스는 서블릿 기술에 종속 X라 재사용성 더 높아짐)

-포워딩 , 인클루딩 대신 메서드 호출로 통신


<h4>3 의존성 주입(DI) - 구현 필요</h4>

<h4>4 DB커넥션풀 - 구현 필요</h4>


<hr>

<h1>컴퓨터 기본 이론 </h1>

<h2>자료구조</h2>

1 처음 메서드가 어디부터 시작하는지 파악하면 좀 덜 막막함

2 원리에 대한 배경지식이 있으면 코딩이 쉬워지고, 이해력 증가

ex) 스택, 큐는 쉽게했는데, LinkedList 구현에서 막힌 이유- LinkedList의 작동원리에 대해 깊게 고민 안 해서

3 노드는 객체 


<h2>정의를 명확히 구체적으로 하는 것이 중요</h2>

4.13 

<h4>1 처음 연결리스트에 대한 정의</h4>

1번 연결리스트는 인접 노드들의 연결로 구성됨 (연결은 어떻게 됨?)

2번 각노드는 넥스트노드와 데이터로 구성된다

-> 이 정의의 한계 : 노드 클래스와 LinkedList 클래스 생성 및 객체 선언까지만 연상 가능

-> 결과: 구현이 막막해짐



<h4>2 추가 연결리스트에 대한 정의-넥스트 노드와 데이터와 노드의 연결에 대해 구체화</h4>

2번 구체화

넥스트 노드(노드에 포함된 객체)

->언제 생성되는가 (평소 안 접해서 생각을 바로 못함 ) -> new Node()

->노드는 자신의 넥스트 노드를 언제 주입받아서 저장하는가 ->setNext()

->노드는 언제 자리 이동을 하는가 ? ->getNext() // (이것은 한방에 생각 안났음)

->언제 소멸되는가 (노드가 아니라 링크드리스트의 역할인듯)

<hr>

1번 구체화

연결리스트(노드 들을 포함한 객체)-틀(컨테이너라고 생각하자)

-> 생성자 (이름의 구성요소는 강제로 가지고 있어야함 -맨처음 연결고리인 head와 여러개 연결되면 크기가 생기니 size가 필요)

-> 추가(주입) void add (물론 노드 객체를 호출해야 저장가능)

-> 삭제(소멸) void remove (물론 노드 객체를 호출해야 소멸가능)

-> 출력 void printList

-> 사이즈(getter & setter)

<h2> 알고리즘 </h2>

기본 알고리즘은 일단 조건문 & 반복문임

근데 이게 눈에 안 들어오는 이유는? -처음 알고리즘이 작용하는 곳 부터 이해를 제대로 못 한 것

가장 간단한 정렬 알고리즘부터 공부하면서 익숙해져야함


<h4> 삽입정렬 정의</h4>

1 내 앞의 숫자들 사이에 삽입하는 정렬 알고리즘


<메인 클래스>

main 함수.

1 정렬할 배열과 그 안의 데이터가 필요 (더미 데이터)

2 sort_insert 함수

3 정렬된 배열 반복문으로 출력

ㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡ

<sort_insert 클래스>

1 반복문 돌리려면 먼저 배열과 사이즈가 준비되어야지

2 그리고 정렬하려면 임시적인 저장공간이 필요.

int sort_insert(삽입할 배열, 배열의 사이즈)

