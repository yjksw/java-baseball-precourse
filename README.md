# 미션 - 숫자 야구 게임

## 🚀 기능 요구사항
- 이 게임은 프로그램이 1에서 9까지 서로 다른 임의의 수 3개를 정하고 이를 플레이어가 맞추는 게임이다.
- 정답을 맞추기 위해 3자리수를 입력하고 힌트를 받는다.
- 힌트는 야구용어인 볼과 스트라이크로 받는데, 같은 자리에 같은 숫자가 있는 경우를 `스트라이크`, 다른 자리에 숫자가 있는 경우를 `볼`로 정한다.
- 같은 숫자가 하나도 없는 경우 힌트로 `낫싱`을 받는다.
  - 예시) 상대방(컴퓨터)의 수가 425일 때, 123을 제시한 경우: 1스트라이크, 456을 제시한 경우: 1볼 1스트라이크, 789를 제시한 경우: 낫싱
- 3자리 숫자가 정답과 같은 경우 게임이 종료된다.
- 게임을 종료한 후 게임을 다시 시작하거나 완전히 종료할 수 있다.
- 아래의 프로그래밍 실행 결과 예시와 동일하게 입력과 출력이 이루어져야 한다.

<br>

## 🛠 상세 기능

* **타겟 숫자 생성** - 랜덤한 1-9까지의 임의 수 3개 생성하기 (중복되지 않는 숫자)
* **사용자 숫자 입력 기능** - 사용자로부터 3자리 수를 입력 받아 변수에 저장하기
  * 해당 입력이 숫자인지 검증
  * 3자리인지 검증
  * 띄어쓰기 혹은 다른 문자없이 입력되었는지 검증
  * 중복되지 않는지 검증
* **힌트 생성 기능** - 입력 숫자와 타겟 숫자를 보고 적절한 힌트를 출력
  * **사용자 입력 숫자와 타겟 숫자 비교 기능** - 사용자의 숫자와 타겟 숫자를 비교하여 (1) 숫자 존재 여부, (2) 해당 숫자 같은 자리 여부를 판단
  * **판단 여부로 힌트 생성 및 출력** - 위의 결과값에 따른 올바른 힌트(`볼`, `스트라이크`, `낫싱` 중 택 1)를 출력
  * **정답일 경우 정답 출력** - 정답 문구를 출력하고 게임 재시작 여부 판단
* **게임오버 혹은 재시작 기능** - 사용자의 입력에 따른 게임 종료 혹은 재시작
  * **사용자에게 판단 여부 입력 받기** - '1 또는 2'를 입력받기 
    * 해당 입력이 숫자인지 검증
    * 1또는 2 숫자인지 검증 
  * **판단 여부로 게임 재시작 혹은 종료하기**

<br>

## ✍🏻 입출력 요구사항
### ⌨️ 입력
- 3자리의 수
- 게임이 끝난 경우 재시작/종료를 구분하는 1과 2 중 하나의 수

### 🖥 출력
- 입력한 수에 대한 결과를 볼, 스트라이크 갯수로 표시
```
1볼 1스트라이크
```
- 하나도 없는 경우 
```
낫싱
```
- 3개의 숫자를 모두 맞힐 경우
```
3스트라이크
3개의 숫자를 모두 맞히셨습니다! 게임 종료
```

### 💻 프로그래밍 실행 결과 예시
```
숫자를 입력해주세요 : 123
1볼 1스트라이크
숫자를 입력해주세요 : 145
1볼
숫자를 입력해주세요 : 671
2볼
숫자를 입력해주세요 : 216
1스트라이크
숫자를 입력해주세요 : 713
3스트라이크
3개의 숫자를 모두 맞히셨습니다! 게임 종료
게임을 새로 시작하려면 1, 종료하려면 2를 입력하세요.
1
숫자를 입력해주세요 : 123
1볼 1스트라이크
… 
```

<br>

## 🎱 프로그래밍 요구사항
- 자바 코드 컨벤션을 지키면서 프로그래밍한다.
  - 기본적으로 [Google Java Style Guide](https://google.github.io/styleguide/javaguide.html)을 원칙으로 한다.
  - 단, 들여쓰기는 '2 spaces'가 아닌 '4 spaces'로 한다.
- indent(인덴트, 들여쓰기) depth를 3이 넘지 않도록 구현한다. 2까지만 허용한다.
  - 예를 들어 while문 안에 if문이 있으면 들여쓰기는 2이다.
  - 힌트: indent(인덴트, 들여쓰기) depth를 줄이는 좋은 방법은 함수(또는 메소드)를 분리하면 된다.
- 3항 연산자를 쓰지 않는다.
- 함수(또는 메소드)가 한 가지 일만 하도록 최대한 작게 만들어라.
- System.exit 메소드를 사용하지 않는다.
- 비정상적 입력에 대해서는 IllegalArgumentException을 발생시킨다.

### 프로그래밍 요구사항 - Application
- Application 클래스를 활용해 구현해야 한다.
- Application의 패키지 구조와 구현은 변경하지 않는다.
- `final Scanner scanner = new Scanner(System.in);`는 변경하지 않는다.
- `// TODO 구현 진행` 이 후 부터 구현한다.

```java
public class Application {
    public static void main(String[] args) {
        final Scanner scanner = new Scanner(System.in);
        // TODO 구현 진행
    }
}
```

### 프로그래밍 요구사항 - RandomUtils
- RandomUtils 클래스를 활용해 랜덤 기능을 구현해야 한다.
- RandomUtils의 패키지 구조와 구현은 변경하지 않는다.

```java
private static final Random RANDOM = new Random();
    private RandomUtils() {
    }
    public static int nextInt(final int startInclusive, final int endInclusive) {
    ...
```

<br>

## 📈 진행 요구사항
- 미션은 [java-baseball-precourse 저장소](https://github.com/woowacourse/java-baseball-precourse) 를 fork/clone해 시작한다.
- 기능을 구현하기 전에 java-baseball-precourse/README.md 파일에 구현할 기능 목록을 정리해 추가한다.
- git의 commit 단위는 앞 단계에서 README.md 파일에 정리한 기능 목록 단위로 추가한다.
  - [AngularJS Commit Message Conventions](https://gist.github.com/stephenparish/9941e89d80e2bc58a153) 참고해 commit log를 남긴다.
- [프리코스 과제 제출 문서](https://github.com/woowacourse/woowacourse-docs/tree/master/precourse) 절차를 따라 미션을 제출한다.

<br>

## 📝 License

This project is [MIT](https://github.com/woowacourse/java-baseball-precourse/blob/master/LICENSE) licensed.
