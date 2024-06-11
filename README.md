# Python program for booking SRT ticket.

매진된 SRT 표의 예매를 도와주는 파이썬 프로그램입니다.  
원하는 표가 나올 때 까지 새로고침하여 예약을 시도합니다.

https://github.com/kminito/srt_reservation 소스코드를 수정하였습니다.

## 다운
```cmd
git clone https://github.com/nuly17/youngnami_srt.git
```
  
## 필요
- 파이썬 3.12에서 테스트 했습니다.

```py
pip install -r requirements.txt
```


## Arguments
    dpt: SRT 출발역
    arr: SRT 도착역
    dt: 출발 날짜 YYYYMMDD 형태 ex) 20240612
    tm: 출발 시간 hh 형태, 반드시 짝수 ex) 06, 08, 14, ...
    num: 검색 결과 중 예약 가능 여부 확인할 기차의 수 (default : 2)
    reserve: 예약 대기가 가능할 경우 선택 여부 (default : False)
    slack: 예약 성공 시 slack으로 메시지 수신 여부 (default : False)
    slack_token: 메시지 수신 받을 slack workspace의 token 정보 ex) sqa_79fe778c7ddec1102273045425984266add82576
    slack_ch: 메시지 수신 받을 slack workspace의 channel 정보 ex) srt 

    station_list = ["수서", "동탄", "평택지제", "천안아산", "오송", "대전", "김천(구미)", "동대구",
    "신경주", "울산(통도사)", "부산", "공주", "익산", "정읍", "광주송정", "나주", "목포"]



## 간단 사용법

회원번호 1234567890  
비밀번호 000000 
동대구 -> 수서, 2024년 06월 12일 오전 6시 이후 기차  
검색 결과 중 상위 2개가 예약 가능할 경우 예약

```cmd
python quickstart.py --user 1234567890 --psw 000000 --dpt 동대구 --arr 수서 --dt 20240612 --tm 06
```

**Optional 1**  
예약대기 사용 및 검색 결과 상위 3개의 예약 가능 여부 확인
```cmd
python quickstart.py --user 1234567890 --psw 000000 --dpt 동대구 --arr 수서 --dt 20240612 --tm 06 --num 3 --reserve True
```
**Optional 2**  
예약 성공 시 slack으로 통보 받기
```cmd
python quickstart.py --user 1234567890 --psw 000000 --dpt 동대구 --arr 수서 --dt 20240612 --tm 06 --num 3 --slack True --slack_token 1111 --slack_ch 2222
```

**실행 결과**

![](./img/img1.png)

## 기타  
명절 승차권 예약에는 사용이 불가합니다.  
