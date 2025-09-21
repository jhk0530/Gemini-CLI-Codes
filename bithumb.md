## 마켓 코드 조회

- https://api.bithumb.com/v1/market/all

```curl
curl --request GET \
     --url 'https://api.bithumb.com/v1/market/all?isDetails=false' \
     --header 'accept: application/json'
```

| 필드명         | 설명                                                                                                                                                      | 타입   |
| -------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- | ------ |
| market         | 빗썸에서 제공중인 시장 정보                                                                                                                               | String |
| korean_name    | 거래 대상 디지털 자산 한글명                                                                                                                              | String |
| english_name   | 거래 대상 디지털 자산 영문명                                                                                                                              | String |
| market_warning | 유의 종목 여부 (NONE: 해당 사항 없음, CAUTION: 거래유의) '유의 종목' 지정 여부에 대해 반환하며, '주의 종목' 지정 여부는 경보제 API를 참고하시기 바랍니다. | String |

## 현재가 정보

- https://api.bithumb.com/v1/ticker

```curl
curl --request GET \
     --url 'https://api.bithumb.com/v1/ticker?markets=KRW-BTC' \
     --header 'accept: application/json'
```

┌─────────────────────┬────────┬──────────────────────────────────────────┐
│ 필드명 │ 타입 │ 설명 │
├─────────────────────┼────────┼──────────────────────────────────────────┤
│ market │ String │ 종목 구분 코드 │
│ trade_date │ String │ 최근 거래 일자(UTC) 포맷: yyyyMMdd │
│ trade_time │ String │ 최근 거래 시각(UTC) 포맷: HHmmss │
│ trade_date_kst │ String │ 최근 거래 일자(KST) 포맷: yyyyMMdd │
│ trade_time_kst │ String │ 최근 거래 시각(KST) 포맷: HHmmss │
│ trade_timestamp │ Long │ 최근 거래 일시(UTC) 포맷: Unix Timestamp │
│ opening_price │ Double │ 시가 │
│ high_price │ Double │ 고가 │
│ low_price │ Double │ 저가 │
│ trade_price │ Double │ 종가(현재가) │
│ prev_closing_price │ Double │ 전일 종가(KST 0시 기준) │
│ change │ String │ EVEN : 보합, RISE : 상승, FALL : 하락 │
│ change_price │ Double │ 변화액의 절대값 │
│ change_rate │ Double │ 변화율의 절대값 │
│ signed_change_price │ Double │ 부호가 있는 변화액 │
│ signed_change_rate │ Double │ 부호가 있는 변화율 │
│ trade_volume │ Double │ 가장 최근 거래량 │
│ acc_trade_price │ Double │ 누적 거래대금(KST 0시 기준) │
│ acc_trade_price_24h │ Double │ 24시간 누적 거래대금 │
│ acc_trade_volume │ Double │ 누적 거래량(KST 0시 기준) │
│ acc_trade_volume_24h │ Double │ 24시간 누적 거래량 │
│ highest_52_week_price │ Double │ 52주 신고가 │
│ highest_52_week_date │ String │ 52주 신고가 달성일 포맷: yyyy-MM-dd │
│ lowest_52_week_price │ Double │ 52주 신저가 │
│ lowest_52_week_date │ String │ 52주 신저가 달성일 포맷: yyyy-MM-dd │
│ timestamp │ Long │ 타임스탬프 │
└─────────────────────┴────────┴──────────────────────────────────────────┘
