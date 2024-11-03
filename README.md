# kotlin-lotto-precourse


## 로또 이야기
우이 프로젝트는 일반 로또와 다른 방식으로 동작합니다!

일반 로또는 모든 번호가 정확하게 일치해야 1등이지만, 이 프로젝트의 로또는 당첨 번호를 가지고만 있어도 당첨으로 인정됩니다.
예를 들어, 당첨 번호가 (1, 2, 3, 4, 5, 6)이고 사용자의 로또 번호가 ( 2, 3, 4, 5, 6, 7)라면 이 로또는 2등으로 인정됩니다.
---
* 로또 사러 가야징~ 요즘 로또 하나에 얼마이더라?
* 1,000원이네!
* 아주머니 여기 1,000원 드릴테니까 로또하나 살게요~
* 네? 1~45자 사이의 번호를 6개 입력해야된다구요?
* 아 중복은 안되구요?
* 나는 당첨번호가 {x,x,x,x,x,x}이렇게랑 보너스는 Y가 나올거 같아! 내가 받은 로또 10장을 한번 긁어볼까? 어? 당첨번호가?̊̈-?̊̈
  1등 → 헉? 당첨번호가 다 맞잖아?
  2등 → 헉? 당첨번호 5개랑 보너스 번호가 맞잖아?
  3등 → 헉? 당첨번호 5개가 맞잖아?
  4등 → 힝 ㅠ 당첨번호 4개가 맞네
  5등 → 그래도 당첨번호 3개나 맞았네!
* 오~! 나는 2번이네!!!
* 아싸~ 30,000,000원!!!!!! 야호~!

---
## 순서
1) 로또구입 -> 구입한 로또 개수 조회(로또 구매 금액 유효성 검사) 
2) 로또 번호 생성하는 곳이 로또 발급 -> 로또 생성 및 보여주기
3) 당첨 번호와 보너스 번호 입력을 받는다.
4) 로또 아주머니가 담첨 번호와 발행한 로또 번호를 비교한다.
5) 로또 판별 기기가 로또의 순위를 비교하여 결과를 계산
6) 로또의 얼마가 당첨 되었는지 보여준다.

```
구입금액을 입력해 주세요.
8000

8개를 구매했습니다.
[8, 21, 23, 41, 42, 43] 
[3, 5, 11, 16, 32, 38] 
[7, 11, 16, 35, 36, 44] 
[1, 8, 11, 31, 41, 42] 
[13, 14, 16, 38, 42, 45] 
[7, 11, 30, 40, 42, 43] 
[2, 13, 22, 32, 38, 45] 
[1, 3, 5, 14, 22, 45]

당첨 번호를 입력해 주세요.
1,2,3,4,5,6

보너스 번호를 입력해 주세요.
7

당첨 통계
---
3개 일치 (5,000원) - 1개
4개 일치 (50,000원) - 0개
5개 일치 (1,500,000원) - 0개
5개 일치, 보너스 볼 일치 (30,000,000원) - 0개
6개 일치 (2,000,000,000원) - 0개
총 수익률은 62.5%입니다.
```
## 기능 목록

- **구매금액 설정** : 사용자는 구매금액을 입력한다. 로또는 1,000원이다
- **로또 발행** : 1~45 사이의 값 중에서 입력한 금액만큼 로또를 발급
     - 1~45 숫자 중 6개를 뽑는다.
     - 6개의 숫자는 중복이 없어야 한다.
- **당첨 번호 설정** : 사용자가 숫자를 입력한다.
  - 당첨번호 5개입력
  - 보너스 번호 1개 입력
- **당첨 확인** : 당첨 번호와 로또번호를 비교하여 당첨 내역을 계산
    - 로또 티켓의 랭킹을 매기고, 일치하는 번호의 개수를 세어 다음과 같은 당첨 금액을 계산합니다:
      - 1등: 6개 번호 일치 / 2,000,000,000원
      - 2등: 5개 번호 + 보너스 번호 일치 / 30,000,000원
      - 3등: 5개 번호 일치 / 1,500,000원
      - 4등: 4개 번호 일치 / 50,000원
      - 5등: 3개 번호 일치 / 5,000원
- **수익률 계산** : 합산한 당첨 금액과 구매급액을 비교하여 수익률을 계산한다. 

## 예외 상황

- 예외 처리
    - [ ] : "[ERROR]"로 시작하는 에러 메시지를 출력 후, Error 메시지를 출력한다.
    - [ ] : 에러가 발생한 부분부터 다시 입력 받는다.
- 입력
    - [ ] : 사용자가 잘못된 값을 입력할 경우 IllegalArgumentException를 발생
- 구입 금액
    - [ ] : 구입 금액이 1,000원 단위가 아닐 경우
    - [ ] : 구입 금액이 숫자가 아닐 경우
- 당첨 번호
    - [ ] : 당첨 번호가 ,로 구분되지 않을 경우
    - [ ] : ,로 구분된 당첨 번호가 숫자가 아닐 경우
    - [ ] : 당첨 번호의 크기가 6개가 아닐 경우
    - [ ] : 당첨 번호가 1 ~ 45 범위가 아닐 경우
    - [ ] : 당첨 번호가 중복될 경우
- 보너스 번호
    - [ ] : 보너스 번호가 숫자가 아닐 경우
    - [ ] : 보너스 번호가 1 ~ 45 범위가 아닐 경우
    - [ ] : 보너스 번호가 당첨 번호와 중복될 경우
- 로또 번호
    - [ ] : 로또 번호의 크기가 6개가 아닐 경우
    - [ ] : 로또 번호가 1 ~ 45 범위가 아닐 경우
    - [ ] : 로또 번호가 중복될 경우
- 수익률
  -  [ ] : 수익률이 소숫점 첫쨰짜리를 넘는 경우