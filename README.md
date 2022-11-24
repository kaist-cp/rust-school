# Rust 겨울학교


- 강의자: [강지훈](https://cp.kaist.ac.kr/jeehoon.kang)
- 시간: 2023/02/08-10 (수-금)
- 주최: [서울대학교 컴퓨터공학부](https://cse.snu.ac.kr/)
- 웹사이트: <https://github.com/kaist-cp/rust-school>, <https://gg.kaist.ac.kr/course/14/>
- 공지: [issue tracker](https://github.com/kaist-cp/rust-school/issues?q=is%3Aissue+is%3Aopen+label%3Aannouncement)


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


## 등록

강의실 준비, 개발 및 채점 서버 준비를 위해 사전 등록을 받고자 합니다.
다음 Google Form을 통해 신청해주시면 감사하겠습니다: TBA


## 구성

다음 두 교과서를 기준으로 강의를 진행할 예정입니다:

- [The Rust Book](https://doc.rust-lang.org/book/)
- Slides (TBA)


일정은 다음과 같습니다:

- 2023/02/08 (수): Rust 익숙해지기

  첫째날은 variable, loop, enum, match, generics과 같은 프로그래밍 개념들을 다룹니다.
  이 개념들은 사실 Rust의 독특한 특징은 아니고 일반적인 고수준 프로그래밍 언어라면 대체로 갖추는 있는 기능입니다.
  이 개념들에 이미 익숙하신 분들은 책만 읽고 오셔도 둘째날부터 참석하시는데 무리가 없으실 것입니다.

  + 13:00-14:15: CS101 복습 (The Rust Book 1-3, 5)
  + 14:30-13:45: 고수준 프로그래밍 기능 (The Rust Book 6, 9, 10.1, 10.2)

- 2023/02/09 (목): 소유권

  둘째날은 Rust의 핵심인 소유권을 다룹니다.
  소유권의 개념과, 이를 기반으로 어떻게 컴파일 시점에 포인터의 안전성을 분석할 수 있는지 설명할 예정입니다.

  + 13:00-14:15: 소유권 개념 (The Rust Book 4)
  + 14:30-13:45: 소유권 기반 타입 시스템 (The Rust Book 10.3)

- 2023/02/10 (금): 소유권 응용

  셋째날은 소유권의 두가지 응용을 다룹니다: 스마트 포인터와 병렬 프로그래밍.
  소유권 기반 타입 시스템을 이용해서 어떻게 두 응용에 대한 안전한 API를 제공할 수 있는지 설명할 예정입니다.

  + 13:00-14:15: 스마트 포인터 (The Rust Book 15)
  + 14:30-13:45: 병렬 프로그래밍 (The Rust Book 16, [Rayon](https://docs.rs/rayon/latest/rayon/))


## 실습

매일 실습 과제가 주어질 것입니다. 채점 서버가 제공될 예정입니다 (TBA).


## 질의 응답

- 강의 중에 아무때나 손들고 질문해주시면 감사하겠습니다.
- 강의 중에 하기 어려운 질문은 (예: 코드에 관한 질문) [issue tracker](https://github.com/kaist-cp/rust-school/issues)를 활용해주세요.


## 사전 준비

효율적인 진행을 위해 겨울학교에 참석하실 분들은 사전에 다음을 준비해주시면 감사하겠습니다.

- Rust 개발 환경 준비

  + 설치: [설치 안내 웹사이트](https://doc.rust-lang.org/book/ch01-01-installation.html)를 보시고 개발 환경을 준비해주세요.
  + 실행: [토이 프로젝트](https://doc.rust-lang.org/book/ch02-00-guessing-game-tutorial.html)를 생성, 빌드, 실행할 수 있는지 확인해주세요.
  + IDE: [Visual Studio Code](https://code.visualstudio.com/)를 추천합니다만, 더 편하신 IDE가 있다면 그걸 쓰셔도 됩니다.
    서버에 접속하실 거라면 [Rust analyzer 플러그인](https://marketplace.visualstudio.com/items?itemName=rust-lang.rust-analyzer)을 설치해주세요.

- Rust 톺아보기

  + ["The Rust Book"](https://doc.rust-lang.org/book/) 1-3장을 읽어와주시면 감사하겠습니다.
    겨울학교에서는 짧은 시간동안 Rust의 소유권 개념과 프로그래밍 도구에 집중할 예정이라,
    Rust의 문법이나 기본적인 도구 사용법은 미리 확인하고 와주시면 효율적인 진행에 매우 큰 도움이 될 것 같습니다.

  + [Rust Playground](https://play.rust-lang.org/) 사용해보기
    인터넷에서 Rust 프로그램을 실행해볼 수 있는 도구입니다.

  + (선택사항) [Compiler Explorer](https://rust.godbolt.org/) 사용해보기
    Rust 프로그램이 어떻게 컴파일되는지 확인해볼 수 있는 도구입니다. 저수준 프로그래밍에 관심있으신 분들은 보셔도 좋을 것 같습니다.

- 실습 준비

  + 이 리파지토리를 clone 받아주세요: `git clone git@github.com:kaist-cp/rust-school.git`

  + 실습 채점 계정을 준비해주세요.
    채점 서버 주소 다음과 같습니다: <https://gg.kaist.ac.kr/course/14/>
    계정 설정 방법은 등록하신 이메일로 보내드릴 예정입니다.

  + (선택사항) 개발 서버 접속

    효율적인 진행을 위해 개발 서버를 빌려드릴 예정입니다만 꼭 제공해드린 서버를 사용하실 필요는 없습니다.
    Visual Studio Code의 Remote Development 기능을 사용해서 접속하시길 추천드립니다.

    `~/.ssh/config`에 아래를 추가하신 다음에:

    ```
    Host rust-school
      Hostname cp-service.kaist.ac.kr
      Port 13003
      User <your-id>
    ```

    `ssh rust-school`을 통해 접속하실 수 있습니다.
    아이디 및 초기 비번은 등록하신 이메일로 보내드릴 예정입니다.
