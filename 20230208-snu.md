# Rust 겨울학교


- 강의자: [강지훈](https://cp.kaist.ac.kr/jeehoon.kang) (KAIST 전산학부)
- 시간: 2023/02/08-10 (수-금)
- 주최: 서울대학교 [컴퓨터연구소](https://ict.snu.ac.kr/), [컴퓨터공학부](https://cse.snu.ac.kr/)
- 웹사이트: <https://github.com/kaist-cp/rust-school>
- 공지: [issue tracker](https://github.com/kaist-cp/rust-school/issues?q=is%3Aissue+is%3Aopen+label%3Aannouncement)
- 채점 서버: <https://gg.kaist.ac.kr/course/14/>


## 소개

[Rust](https://www.rust-lang.org/)는 안전한 고성능 소프트웨어를 작성하기에 매우 용이한 프로그래밍 언어입니다.
Java와 같이 안전한 소프트웨어를 작성하기에 용이한 프로그래밍 언어도 있고, C/C++과 같이 저수준 고성능 시스템 소프트웨어를 작성하기에 용이한 프로그래밍 언어도 있지만,
안전성과 고성능 두 마리 토끼를 모두 잡은 프로그래밍 언어는 Rust가 거의 유일하다고 할 수 있습니다.
이를 위한 핵심 아이디어는 *소유권*이라는 개념을 사용하여 포인터의 안전성을 컴파일 시점에 검증하는 타입 시스템입니다.

이러한 장점 덕택에 Rust는 [Mozilla](https://www.mozilla.org/), [Amazon AWS](https://aws.amazon.com/), [Cloudflare](https://www.cloudflare.com/), [FuriosaAI](https://www.furiosa.ai/)를 비롯한 대기업 및 딥테크 스타트업에서 널리 사용되고 있습니다.
프로그래밍 도구도 활발히 개발되어 라이브러리 생태계, 빌드 시스템, language server / IDE, linter, 컴파일러 에러 메시지, 비동기 프로그래밍 등은 오히려 오랜 역사를 가진 C/C++보다 나은 면도 있을 정도입니다.

이번 겨울학교는 Rust의 소유권 개념을 공부하고 또 실습을 통해 손에 익히는 것을 목표로 합니다.
효율적인 진행을 위해 [CS101](https://cs101.kaist.ac.kr/)과 같은 프로그래밍 입문 교과목을 수강하였거나 비슷한 지식을 가진 분들을 대상으로 합니다.
겨울학교를 통해 Rust에 익숙해지시고 앞으로 하실 개발과 연구에 도움이 되시길 간절히 바라겠습니다.


## 구성

다음 두 교과서를 기준으로 강의를 진행할 예정입니다:

- [The Rust Book](https://doc.rust-lang.org/book/)
  + [한국어 버전](https://rinthel.github.io/rust-lang-book-ko/)
- [Slides](https://docs.google.com/presentation/d/1LbiQ1Z3FTjp1144GRwEj3EPNj-RspAthlsq3a0PCQHw/edit?usp=sharing)


일정은 다음과 같습니다:

- **사전 준비: 프로그래밍 기초 개념**

  겨울학교가 시작하기 전에 프로그래밍 기초 개념을 자습하고 와주시길 부탁드립니다 (The Rust Book 1-3, 5, 6, 9, 10.1, 10.2).
  변수, 함수, if, loop 등 다른 언어에도 널리 쓰이는 개념이니 쉽게 자습하실 수 있으리라 생각합니다.
  **겨울학교가 시작하기 전에 아래 "사전 준비" 항목을 이행하시길 부탁드립니다.**

- **2023/02/08 (수): 프로그래밍 기초 개념 복습 및 소유권**

  첫째날은 프로그래밍 기초 개념을 복습한 다음 Rust의 핵심 개념인 소유권을 다룹니다.
  소유권은 Rust 핵심 개념으로써 컴파일 시점에 성능 오버헤드 없이 포인터의 안전성을 분석하는 기법입니다.
  소유권은 앞으로 진행할 강의의 이론적 기반이니 가급적 첫째날부터 참석해주시길 부탁드립니다.

  + 13:00-14:15: 프로그래밍 기초 개념 복습 (The Rust Book 1-3, 5, 6, 9, 10.1, 10.2)
  + 14:30-15:45: 소유권 개념 및 타입 시스템 (The Rust Book 4, 10.3)

- **2023/02/09 (목): 함수와 스마트 포인터의 소유권 분석**

  둘째날은 소유권 개념을 기반으로 함수와 스마트 포인터의 안전성을 분석합니다.
  Rust에서 값으로써의 함수와 (closure, anonymous function) 스마트 포인터는 (smart pointer)
  (1) C++과 같이 성능 오버헤드가 없거나 매우 작으면서도 (2) Java와 같이 컴파일 시점에 이미 안전성이 보장됩니다.
  이를 소유권 개념을 이용해서 분석합니다.

  + 13:00-14:15: 함수의 소유권 (The Rust Book 13)
  + 14:30-15:45: 스마트 포인터의 소유권 (The Rust Book 15)

- **2023/02/10 (금): 컴파일 시점 소유권 분석 + 실행 시점 소유권 검증**

  셋째날은 실행 시점에 소유권을 검증하는 기법을 소개하고 이를 컴파일 시점 소유권 분석 결과와 결합하는 하이브리드 방법론을 다룹니다.
  시스템 프로그램의 복잡성으로 인해 실행중에 나타나는 모든 현상을 컴파일 시점에 안전성을 분석해낼 순 없습니다.
  이를 보완하기 위한 방안으로써 실행 시점 소유권 검증의 핵심 기법인 interior mutability을 다루고, 스마트 포인터의 안전성을 재검토합니다.
  또한 하이브리드 방법론의 예로써 동시성/병렬성 프로그래밍 라이브러리를 검토합니다.

  + 13:00-14:15: 실행 시점 소유권 검증
  + 14:30-15:45: 동시성/병렬성 프로그래밍 (The Rust Book 16, [Crossbeam](https://docs.rs/crossbeam/latest/crossbeam/), [Rayon](https://docs.rs/rayon/latest/rayon/))


## 실습

매일 실습 과제가 주어질 것입니다. [채점 서버](https://gg.kaist.ac.kr/course/14/)를 통해 제출해주세요.


## 질의 응답

- 강의 중에 아무때나 손들고 질문해주시면 감사하겠습니다.
- 강의 중에 하기 어려운 질문은 (예: 코드에 관한 질문) [issue tracker](https://github.com/kaist-cp/rust-school/issues)를 활용해주세요.


## 사전 준비

효율적인 진행을 위해 겨울학교에 참석하실 분들은 사전에 다음을 준비해주시면 감사하겠습니다.

- 채점 서버 계정 확인

  + 채점 서버: https://gg.kaist.ac.kr/course/14/
  + 계정 확인: "Forgotten your password or username?" 누르신 후 등록하신 이메일을 입력하세요.

- Rust 개발 환경 준비

  + 설치: [설치 안내 웹사이트](https://doc.rust-lang.org/book/ch01-01-installation.html)를 보시고 개발 환경을 준비해주세요.
  + 실행: [토이 프로젝트](https://doc.rust-lang.org/book/ch02-00-guessing-game-tutorial.html)를 생성, 빌드, 실행할 수 있는지 확인해주세요.
  + IDE: [Visual Studio Code](https://code.visualstudio.com/)를 추천합니다만, 더 편하신 IDE가 있다면 그걸 쓰셔도 됩니다.
    서버에 접속하실 거라면 [Rust analyzer 플러그인](https://marketplace.visualstudio.com/items?itemName=rust-lang.rust-analyzer)을 설치해주세요.

  + (선택사항) 실습 서버 접속
  
    효율적인 진행을 위해 개발 서버를 빌려드릴 예정입니다만 꼭 제공해드린 서버를 사용하실 필요는 없습니다.
    Visual Studio Code의 Remote Development 기능을 사용해서 접속하시길 추천드립니다.

    `~/.ssh/config`에 아래를 추가하신 다음에:

    ```
    Host rust-school
      Hostname cp-service.kaist.ac.kr
      Port 13003
      User <your-id>
    ```

    터미널에서 `ssh rust-school`을 통해 접속하실 수 있습니다.

    + 아이디: [채점 서버](https://gg.kaist.ac.kr/course/14/) 아이디와 같음
    + 비밀번호: <https://gg.kaist.ac.kr/event/25/> "Your token"


- Rust 톺아보기

  + ["The Rust Book"](https://doc.rust-lang.org/book/) 1-3장을 읽어와주시면 감사하겠습니다.

    겨울학교에서는 짧은 시간동안 Rust의 소유권 개념과 프로그래밍 도구에 집중할 예정이라,
    Rust의 문법이나 기본적인 도구 사용법은 미리 확인하고 와주시면 효율적인 진행에 매우 큰 도움이 될 것 같습니다.

  + [Rust Playground](https://play.rust-lang.org/) 사용해보기

    인터넷에서 Rust 프로그램을 실행해볼 수 있는 도구입니다.

  + (선택사항) [Compiler Explorer](https://rust.godbolt.org/) 사용해보기

    Rust 프로그램이 어떻게 컴파일되는지 확인해볼 수 있는 도구입니다. 저수준 프로그래밍에 관심있으신 분들은 보셔도 좋을 것 같습니다.

- 실습 실습 리파지토리 다운로드
  
  터미널에서 다음을 실행해주세요:

  ```
  git clone git@github.com:kaist-cp/rust-school.git
  ```

- 사전 숙제

  아래 문제를 해결하고 [채점 서버](https://gg.kaist.ac.kr/course/14/)를 통해 제출해주세요.

  + <https://github.com/kaist-cp/cs220/blob/main/src/assignments/assignment02.rs>
  + <https://github.com/kaist-cp/cs220/blob/main/src/assignments/assignment03.rs>
  + <https://github.com/kaist-cp/cs220/blob/main/src/assignments/assignment06.rs>
