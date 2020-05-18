# R-code-for-finance
R code for finance <br>
주식, 재무표, 데이터를 위해 만든 repo입니다. 

# 2020.04.28 UPDATE
1.시황이 업데이트되었습니다.
- 기존에 function형태로 제공했던 마감시황이 RMD, r마크다운 형식으로 제공합니다. <br>
- 미국 뿐만 아니라 유럽주요국, 중국, 일본, 대만, 한국, 금, 국제유가 정보를 제공합니다. <br>
- 기존에 제공하던 가격그래프를 1분 단위가격(intra day)으로 제공하여 보다 세밀하게 볼 수 있도록 변경하였습니다 <br>
- 미국의 경우 마감시황과 개장시황을 제공합니다. 일정 시간이 되면 개장시황이 마감시황으로 변경됩니다 <br>
- 기존에 제공하던 시황은 삭제하였습니다. <br>

# 2020.03.01 UPDATE
1.한경 컨센서스가 업데이트 되었습니다.
- 한경컨센서스에서 제공하는 증권 리포트를 열람할 수 있는 함수입니다. <br>
- 함수는 hk_consensus(categ,start_date,end_date)로 구성되어 있습니다. <br>
- categ는 마켓, 산업, 파생 등을 지정해 주는 요소이며, start_date와 end_date는 발행 시점과 끝지점을 의미합니다. <br>
- 자세한 사용법은 하단에 "코드이용방법"을 참고해주시기 바랍니다 <br>

# 2019.10.02 UPDATE
1.[한국] 기업정보 가 업데이트 되었습니다
- 주말동안 반복하여 금요일 데이터가 뜬 에러를 수정하였습니다 <br>
- 차트 하단에 뜨던 차트범위를 제외하였습니다. <br>
- 실행시 콘솔에 뜨던 warn 메세지를 제외하여 가독성을 늘렸습니다. <br>
- 차트에 볼린져밴드, 볼륨프로파일(매물대) 보조지표를 추가하였습니다 <br>
- 차트 상단에 현재가가 뜨도록 수정하였습니다. 현재가는 시간대 거래가를 의미하며 장중시간에는 최종 거래 가격으로 설정하였습니다. <br>
- OHLC정보에 등락율과 거래량을 추가하였습니다 <br>

# 2019.10.02 UPDATE
1.시황이 업데이트 되었습니다
- 휴장시 시황이 뜨지 않던 문제를 해결하였습니다 <br>
- 기존 시황 중 골드가격 시황을 제외하였습니다. <br>

# 2019.09.09 UPDATE
1.시황이 업데이트 되었습니다
- 미국,국제유가,골드시세,중국,일본,대만,한국시장의 시황을 제공합니다 <br>
- 자세한 이용방법은 아래 '코드이용방법'을 참고하시기 바랍니다 <br>

# 2019.05.06 UPDATE
1. 중국상장기업목록이 업로드 되었습니다.
- 전 중국종목의 간략한 기업정보와 종목코드를 제공합니다 <br>

# 2019.04.28 UPDATE
1. 중국상장기업 기업정보가 업로드 되었습니다.
- 중국상장기업의 기본재무정보, 뉴스 및 공시, 주가정보를 제공합니다 <br>
- 이용방법은 아래 '코드이용방법'을 참고하시기 바랍니다 <br>

# 2019.04.19 UPDATE
1. 마감시황 업데이트 되었습니다.
- 금/은 시세란에 오류가 걸려 뜨지 않던 에러를 "이용할 수 없음"으로 대체하였습니다 <br>

2. 한국기업정보코드가 업데이트 되었습니다.
- 주가차트에 기업명이 뜨도록 수정하였습니다 <br>
- 기업정보에 기존에 없었던 "뉴스 및 공시" 란을 추가하였습니다.<br>
  ㄴ 최대 5개의 뉴스 및 공시가 뜨도록 추가하였습니다.<br>

# [코드 이용방법]
# MARKET REPORT.rmd
- 따로 사용법 없이 rmd파일을 import시켜 도큐형태 혹은 html로 export하시면 됩니다. <br>
- 1분단위 가격을 이용하여 그래프를 나타냅니다. <br>
- 전일보다 하락하면 파란색, 상승시 빨간색 그래프를 나타내도록 하였습니다. <br>
- 분당 가격 그래프의 시간대는 중국기준으로 설정되어 있습니다. <br>
- 크롤링을 위주로 작성되어 로딩속도가 느립니다. 하루빨리 속도를 개선하도록 하겠습니다. <br>

# 한경컨센서스
- 함수는 hk_consensus(categ, start_date, end_date) 로 구성되어 있습니다. <br>
- categ 는 산업, 파생, 시장 등을 구성하는 요소이며, input은 다음과 같습니다. <br>
- categ input: 파생상품:'d', 산업:'i', 경제:'e', 시장:'m', 기업:'b'  <br>
- 만일 2020년 02월 14일 부터 2020년 02월 17일 까지 "경제" 리포트를 보길 원하신다면 hk_consensus("e",'2020-02-14','2020-02-17')을 입력해주시면 됩니다. <br>
- 오늘 "경제" 리포트를 보길 원하신다면 start_date와 end_date를 입력하지 않고 hk_consensus("e")만 입력 해 주시면 됩니다. <br>
- console창에 함수를 입력해 주시면 해당 날짜와 해당 카테고리의 목록이 테이블 형태로 나타나며, 열람하고 싶은 리포트 맨 앞 숫자를 입력하시면 브라우져의 새 창 형식으로 pdf가 띄어집니다. <br>
- 열람 후 '계속 열람하시겠습니까?'라는 질문이 뜰 y를 입력할 시 계속해서 해당 업종에 대한 리포트를 열람하실 수 있습니다. <br>


# 중국상장기업목록
- 중국상장기업목록은 중국 본토 내 상장되어 있는 전 기업의 간단한 정보를 제공합니다. <br>
- function화 시켜 SHSZ_table()로 작동하고, csv파일로 저장하고 싶으면 SHSZ_table(save_csv_file=TRUE)를 입력하시면 됩니다 <br>
- 시간이 오래걸리므로 sheet만 참고하고 싶으시면 https://docs.google.com/spreadsheets/d/1AxvMtxLIJUWyfXUgM_LLo5XV5Bj7ODqcu6JMEtBelE4/edit?usp=sharing 를 보시면 됩니다.

- 중국상장기업 기업정보는 중국 A주에 상장되어있는 기업의 정보를 제공합니다. 이용방법 : 예)cn_get_st('000002') <br>
- A주종목을 대상으로 하였으므로 "2" 혹은 "9"로 시작하는 B주 종목코드는 실행이 불가합니다 <br>
- 홍콩상장기업 재무제표와 중국상장기업 제무제표는 홍콩재무제표, 중국재무제표를 나타냅니다. <br>

- 홍콩상장기업 재무제표와 중국상장기업 재무제표 내 주식코드 테이블은 그냥 참고용이지, function과는 독립적이므로 원치 않으신 분들은 function만 import해도 됩니다. <br>

- 중국상장기업 재무제표 이용방법 : cn_fs('코드번호') ex) cn_fs('000002') <br>

# k-score
- k-score는 알트만의 z-core를 본 떠 만든 한국형 모델 k-score입니다. 상장되어 있는 전 종목에 이 모델을 적용시키는 코드이며, 한눈에 기업의 부실정도를 측정가능하도록 하는 모델입니다.<br>
reference: <br>
[1] https://m.blog.naver.com/PostView.nhn?blogId=haan79&logNo=10158008764&proxyReferer=https%3A%2F%2Fwww.google.co.kr%2F<br>
[2] https://finata.blog.me/221191125946

- 한국상장기업 기업정보는 한국 상장기업에 대한 기본 정보를 제공합니다. 코드이용방법 : kr_get_st('6자리코드') 예) kr_get_st('005930')<br>

