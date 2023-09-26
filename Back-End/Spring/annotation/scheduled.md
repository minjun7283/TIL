# @Scheduled

## 스케줄러란?
일정한 시간간격 또는 특정시간에 특정로직을 가동시키기 위해 사용하는 것이 scheduler이다. 


spring에 대해 공부하다보니 1일 1위해 참여하는 서비스의 로직을 어떻게 짜는지 궁금하여 찾아보다보니 scheduler라는 것을 발견하게 되었다.

## Scheduler 사용방법

아래의 사진처럼 application 클래스에 @EnalbeScheduling 어노테이션을 달아준다.

![image](https://github.com/minjun7283/TIL/assets/107666764/2a9d8920-14bd-454b-a4cd-7dea3d28dc38)


그리고 자신이 Scheduler를 사용할 메서드에 @Scheduled 어노테이션을 달아주면 된다.

![image](https://github.com/minjun7283/TIL/assets/107666764/9567e8bf-e8f9-4771-a6ad-2b60d87f2b5e)

## @Scheduled 사용조건
1. @Scheduled를 사용할 메서드는 반환타입이 void이여야 하고 Parameter를 줄 수 없다.
2. @Scheduled는 아래 설정 중 하나를 적용시켜줘야 한다.

## @Scheduled 설정

- cron : 크롬표현식을 사용하여 스케줄링한다.

```
@Scheduled(cron = "0 0 0 * * *") 
```
순서대로 분 ,시 ,일 ,월 ,요일 ,년을 나타낸다.

- fixedDelay / fixedDelayString 이전 작업이 종료되고 다시 시작하는 시간(대기 시간)
```
@Scheduled(fixedDelay = 5000 또는 fixedDelayString = "5s")
```
이전 작업 완료 후 5초 뒤 다시 동작

- fixedRate / fixedRateString 이전 작업종료와 무관하게 설정된 시간 간격대로 실행한다.
```
@Scheduled(fixedRate = 5000 또는 fixedRateString = "5s")
```
한번 실행한 이후부터 5초간격으로 실행한다.


- initalDelay /initalDelayString 처음 실행되었을때의 딜레이 시간
```
@Scheduled(initalDelay = 5000 또는 initalDelayString = "5s")
```
app 실행완료 후 5초뒤 실행

