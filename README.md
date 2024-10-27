# 2주차 미션 - 자동차 경주

## 🤔 1주차 회고

- 1주차의 목표는 깃 커밋 컨벤션 익히기, 최대한 알기 쉽게 작성하기, 주석 적극 활용하기, 오버 엔지니어링 하지 않기였다.
- 얼렁뚱땅 하고 제출할 때에는 나름 잘 작성하였다고 생각했는데, 코드 리뷰를 하고 돌아보니 내 코드는 악취가 엄청났다.

  ![아 냄쌔](nemsae.png)

- 2주차에서는 다음 목표를 가지고 진행할 것이다.
    - readMe에는 필요한 부분만 깔끔하게 정리하기
    - 주석을 덜 사용하고, 코드만으로 이해할 수 있게 잘 작성하기
    - 일급 컬렉션 사용하기
    - MVC 패턴 적용하기

## 🤓 1주차 공통 피드백 - 내가 지키지 못한 것

- 커밋 메시지를 의미 있게 작성하자
  > [좋은 git 커밋 메시지를 작성하기 위한 7가지 약속](https://meetup.nhncloud.com/posts/106)
- 변수/함수/클래스 이름 짓는 데에 고민하자
    - 연속된 숫자를 덧붙이거나(a1, a2, ..., aN), 불용어(Info, Data, a, an, the)를 추가하는 방식은 적절하지 못하다.
- 축약하지 말자
    - 의도를 드러낼 수 있다면 이름이 길어져도 괜찮다.
- 공백도 코딩 컨벤션이다
- 의미 없는 주석을 달지 말자
- 배열 대신 컬렉션을 사용하자
    - Java에서 제공하는 API를 적극 활용한다.

## 🔍 프로그래밍 요구사항

- indent가 3이 넘지 않도록 구현한다.
- 3항 연산자를 쓰지 않는다.
- 메서드가 한 가지 일만 하도록 최대한 작게 처리한다.
- JUnit 5와 AssertJ를 이용하여 테스트를 수행한다.

## ✔️ 기능 요구사항

- 주어진 횟수 동안 전진하는 자동차들 중 우승자를 구하는 자동차 경주 게임
    - 사용자는 자동차들의 이름과 시도할 횟수를 입력한다.
        - 자동차 이름은 쉼표(,) 기준이며, 5자 이하이다.
    - n대의 자동차는 전진하거나 가만히 대기한다.
        - 0~9 사이의 무작위 값이 4 이상인 경우 자동차는 전진한다.
    - 게임이 완료된 후 우승자를 출력하며, 우승자가 여러 명인 경우 쉼표(,)를 이용하여 구분한다.
    - 잘못된 값을 입력할 경우 `IllegalArgumentException` 을 발생시킨 후 애플리케이션을 종료한다.

## 📜 기능명세서

### 입력

- [x] 자동차 입력 안내 문구를 출력한다.
- [x] 사용자는 경주할 자동차 이름을 입력한다.
- [x] 시도할 횟수 입력 안내 문구를 출력한다.
- [x] 사용자는 시도할 횟수를 입력한다.

> 사용자 입력은 `camp.nextstep.edu.missionutils.Console`의 `readLine()`을 활용한다.

### 입력 검증

- [x] 사용자가 자동차 이름을 올바르게 입력했는지 검증한다.
- [x] 사용자가 시도할 횟수를 올바르게 입력했는지 검증한다.

### 게임 진행

- [x] 입력된 자동차 이름들을 저장한다.
- [x] for 문으로 입력된 시도 횟수만큼 라운드를 진행한다.
- [x] 각 자동차에 대해 랜덤 값을 할당한다.
  > 랜덤 값 추출은 `camp.nextstep.edu.missionutils.Randoms`의 `pickNumberInRange()`를 활용한다.
- [x] 랜덤 값이 4 이상이면 전진시킨다.

### 전역 상수 설정

- [x] 하드코딩을 피하고 전역 상수를 설정한다.

### 예외 처리

- [x] `IllegalArgumentException` 외에 발생한 예외는 `IllegalArgumentException` 으로 변환하여 다시 던진다.
- [x] 상위 메서드에서 `IllegalArgumentException` 예외를 잡아 예외 정보를 출력한다.

### 출력

- [x] 실행 결과를 출력한다.
- [x] 최종 우승자를 출력한다.

## 👀 제출 전 과제에 대한 한 줄 평

- 과제를 시작하기 전에 세웠던 목표를 돌아보겠습니다.

1. readMe에는 필요한 부분만 깔끔하게 정리하기

- 첫번째 주차에서는 과제 자체에 대한 내용도 담으려다 보니 너무 양이 많아졌고, 핵심이 뭔지 파악하기 힘들었습니다.
- 이번에는 과제 내용 자체는 이해한 내용만 짧게 쓰고, 이전 과제에 대한 회고나 목표만을 추가하였습니다.
- 덕분에 전보다 잘 정리된 readMe를 완성할 수 있었습니다.

2. 주석을 덜 사용하고, 코드만으로 이해할 수 있게 잘 작성하기

- 첫번째 주차에서 주석을 최대한으로 사용하려 했던 이유는 프로그래밍을 모르는 사람이 봐도 이해할 수 있게 하기 위해서였습니다.
- 그러나 프로그램을 요구하는 고객들도 결과만을 요구하지, 이해할 수 있는 프로그램을 만들어달라고는 하지 않습니다.
- 따라서 이번 과제에서는 주석을 아예 사용하지 않았고, 대신 변수명이나 메서드명 짓기, 로직 분리하기에 시간을 들여 **코딩을 하는 사람**이 이해할 수 있도록 작성했습니다.

3. 일급 컬렉션 사용하기

- 첫번째 과제에서는 구분자 배열을 선언했었는데, 만약 확장되어야 하는 상황이 주어진 경우 배열 자체의 조작에 있어 잘못된 사용을 하게 될 위험이 있었습니다.
- 이를 막기 위해 일급 컬렉션을 학습하고, 객체를 안전하게 사용할 수 있도록 설계했습니다.

4. MVC 패턴 적용하기

- 마찬가지로 첫번째 과제에서는 프로그램의 난이도, 구현량이 낮았기 때문에 MVC 패턴을 적용하지 않고 구현했고 덕분에 복잡도는 크게 증가하지 않았습니다.
- 이번 과제에서는 메서드의 책임을 최대한 분리하게 하기 위해서 MVC 패턴을 도입했습니다.
- 전보다 복잡도는 증가하였지만 각 클래스의 역할을 명확하게 구분할 수 있게 되었고, 확장성 또한 좋아졌습니다.

<br>

- 위와 같은 목표들을 정하고 달성하면서 확실히 프로그램의 질이 높아졌다고 느꼈습니다.
- 자바라는 언어 자체에는 조금 서먹했었는데 이번 과제를 통해 조금 친해진 것 같습니다.
- 지금까지 TDD 없이 프로그램 구현 후 일괄적으로 테스트 케이스를 추가하였는데, TDD 도입에 대해서는 조금 회의적입니다.<br>왜냐하면 처음에 많은 케이스들을 정의하더라도, 프로그램을 구현하면서 고려하지 못한
  경우들이 반드시 나오기 때문입니다.<br>그래서 TDD 도입은 커뮤니티를 통해 고민해봐야 할 것 같습니다.