# 월드 오브 워크래프트 아바타 로그 데이터 분석

<p float="left" align="center">
  <img src="/img/wow-title.jpeg" alt="wow_title" style="zoom:70%;" width="70%"/> 
</p>



### 월드 오브 워크래프트

* MMORPG(Massively Multiplayer Online Role-Playing Game) 게임으로 대규모의 유저가 동시에 접속해 플레이하는 게임.
* 자유도가 높은 반면 라이트 유저에게 진입장벽이 낮다는 것이 단점.
* 종족 간 대결과 협력을 바탕으로 한 탄탄한 스토리와 세계관이 설계된 게임.
* 얼라이언스/호드라는 커다란 종족 분류 아래 세분화된 종족이 있으며, 전사, 마법사 등 직업도 13가지로 세분화됨. 
* 월정액제로 운영되고 있어 매출면에서 유저들이 꾸준히 접속하는 것이 무엇보다 중요함

​    

### 데이터

* 대만 연구진이 3년간 수집한 데이터로, 연구진은 게임 플레이어를 생성해 10분 간격으로 데이터를 수집함. 
* 대만 Light’s Hope 영역에서 데이터를 수집했으며, 서버 내 같은 faction(이 경우엔 호드)의 플레이어 정보만 수집 가능.
* 한번에 수집할 수 있는 데이터가 제한돼 있기 때문에 종족, 직업, 레벨을 다르게 설정해 여러번에 나눠 수집했다고 함.
* 이번 분석에서는 2008년 데이터를 가공한 kaggle 버전를 분석함.
* 2008년에는 11월 13일 리치왕의 분노 확장팩이 출시돼 큰 변화가 발생함. 
* 최고 레벨이 70에서 80으로 증가하고 the death knight라는 새로운 직업이 나옴.

#### 	변수

- 유저 아이디, 종족, 직업, 접속 시간, 해당 시점의 레벨, 위치 지역, 길드 정보를 수집함.
- 아이디와 길드 이름 등은 익명 처리돼 있음.

​    

### 유저 활동 지표

#### DAU

<p float="left" align="center">
  <img src="/img/dau.png" alt="dau" style="zoom:70%;" width="70%"/> 
</p>

* DAU는 전체 유저 대비 5% 수준(평균 1964명)

* 10월 8일 사용자 수가 급등한 것은 대규모 패치가 예고 되면서 기대감이 반영된 것
* 10월 7일에 리치 왕의 분노를 준비하기 위한 3.0.2 패치 '파멸의 메아리’에 대한 예고가 나옴

#### Stickiness

<p float="left" align="center">
  <img src="/img/stickiness.png" alt="stickiness" style="zoom:70%;" width="70%"/> 
</p>

* stickiness는 평균 24% 수준
* 2008년 초 25%-30%를 유지하다가 10월 들어 10% 초반으로 급락함
* 리치왕의 분노 확장팩 릴리즈 후인 11월 말부터 상승하는 추세로 돌아섬

#### 신규 유저 수

<p float="left" align="center">
  <img src="/img/new_users_perc.png" alt="new_users" style="zoom:70%;" width="70%"/> 
</p>

* 매일 평균 54명의 신규 유저가 게임에 진입함. DAU 대비 2.6% 수준.
* 10월 8일 신규 유저 비율이 47%로 급등한 것 역시 리치왕의 분노 확장팩 출시에 대한 기대감이 반영된 것으로 보임.

​    

### 리텐션 분석

<p float="left" align="center">
  <img src="/img/retention.png" alt="retention" style="zoom:70%;" width="70%"/> 
</p>

* Day1 리텐션은 28% 수준이며 Day8 이후 15% 아래로 떨어짐. 또한 Day 50 이후에는 대체로 9% 이하의 리텐션 수준을 보여줌. 단, 몇 번의 예외를 제외하면 5% 아래로 하락하는 경우는 적음.
* Day300까지 리텐션이 서서히 감소 또는 유지 흐름을 보이다가 Day330 이후로 리텐션 수준이 다시 상승했음. 확장팩 릴리즈의 영향으로 해석됨.



#### 길드 가입 여부에 따른 리텐션 수준

<p float="left" align="center">
  <img src="/img/retention_guild_join.png" alt="retention_guild_join" style="zoom:70%;" width="60%"/> 
  <img src="/img/retention_daily_guild.png" alt="retention_daily_guild" style="zoom:70%;"  width="60%"/>
</p>

* 모든 기간에 걸쳐 길드에 가입한 유저의 리텐션이 그렇지 않은 유저의 리텐션보다 높음.
* 길드 가입한 유저의 리텐션은 평균 43%인반면 길드 없는 유저들의 리텐션은 평균 7.5%에 그침.
* 길드에 가입한 경우 Day150 전까지는 20%이상의 리텐션 수준을 보여주며, Day330 이후 리텐션이 다시 상승함.
* 길드에 가입하지 않은 유저의 경우 Day12 이후 리텐션이 2-3% 수준으로 낮음. Day330 이후에도 거의 상승하지 않음.

#### 길드 크기에 따른 리텐션 수준

<p float="left" align="center">
  <img src="/img/retention_guild_size.png" alt="retention_guild_size" style="zoom:70%;" width="70%"/> 
</p>

* 23명(길드 규모 평균)을 기준으로 대규모 길드와 소규모 길드를 나눔.
* 길드 규모에 따라 day N 리텐션 비율이 어떻게 달라지는지 집계함.
* 대규모 길드에 소속된 유저의 리텐션이 소규모 길드 소속 유저보다 전 기간에 걸쳐 높음. 
* 평균적으로 대규모 길드 유저의 리텐션은 21%, 소규모 길드 유저의 리텐션은 17%로 대규모 길드가 4%p 높음.

​    

### 퍼널 분석

<p float="left" align="center">
  <img src="/img/funnel_entire.png" alt="funnel_entire" style="zoom:70%;" width="70%"/> 
</p>

* 10-20 레벨에서의 전환율이 19%로 가장 낮음. 레벨 10을 넘어가기가 어렵다는 것을 보여줌.
* 나머지 구간의 전환율은 대부분 80% 후반이거나 90%로, 레벨 10 이상을 달성하면 레벨 70까지 중도 이탈하는 유저는 적음.
* 레벨 70-80 구간은 리치왕의 분노(WotLK) 확장팩에서 추가된 것이어서 전환율이 낮게 나타난 것으로 보임.

#### 확장팩 런칭 전/후 비교

<p float="left" align="center">
  <img src="/img/funnel_lk_or_not.png" alt="funnel_lk_or_not" style="zoom:70%;" width="70%"/> 
</p>

* 리분(WotLK) 런칭 이후 모든 단계의 전환율이 상승함. 레벨 10 이상을 달성하는 유저도 19%에서 24%로 5%p 증가함.
* 또한 10-20, 60-70 구간을 제외하고 모든 구간에서 전환율이 90% 이상을 달성함.
* 새로 개설된 70-80 레벨 구간까지 진입한 유저도 이전 단계 대비 50퍼센트 이상으로 확인됨.

​    

### 이탈율 분석

<p float="left" align="center">
  <img src="/img/churn_rate.png" alt="churn_rate" style="zoom:70%;" width="70%"/> 
</p>

* 90일 이상 접속하지 않은 유저를 이탈한 유저로 규정함.
* 이탈율은 평균 3.2% 수준이며, 2008년 6월까지는 항상 5% 미만을 기록함.    
* 그러나 이후 다소 증가하는 추세이며, 7월 22일에는 7.7%로 가장 높은 수치를 기록함. 

#### 레벨별 이탈 수준

<p float="left" align="center">
  <img src="/img/churn_level.png" alt="churn_level" style="zoom:70%;" width="70%"/> 
</p>

* 레벨 10 이하에서 많이 떠나므로 레벨 10까지 도달하게 만드는 것이 중요        
* 레벨 60에서도 다소 떠난 유저가 많아 게임을 지속할 새로운 요인을 제공할 필요가 있음.
* 최고 레벨인 70 이후에 떠나는 유저들은 더이상 할 것이 없어서 떠나는 것으로 보임.

#### 이탈율 상위 지역

<p float="left" align="center">
  <img src="/img/zone_churn.png" alt="zone_churn" style="zoom:70%;" width="70%"/> 
</p>

* 지역별로 해당 지역에서의 활동을 마지막으로 이탈한 유저의 비율을 계산함.
* 세데크 전당, 오그리마 전설의 전당, 폭풍우 요새, 검은 사원 등이 상위권을 차지함. 이들 지역은 보상이 별로 없거나 난이도가 너무 높아 인기가 없음. 폭풍우 요새와 검은 사원 등은 추후 입장 퀘스트가 없어짐.
* 단 유입 규모 자체가 적은 지역이라 이탈율이 과대 평가되는 측면이 있음. 유저 규모가 1000명 이상인 경우를 대상으로 재분석 실시함.

#### 이탈율 상위 지역(대규모 지역)

<p float="left" align="center">
  <img src="/img/zone_churn_large.png" alt="zone_churn_large" style="zoom:70%;" width="70%"/> 
</p>

* 유저 규모 1000명 이상인 지역에서 이탈율 상위 지역 분석
* 영원노래의 숲, 멀고어, 티리스팔 숲, 불모의 땅, 실버문 등에서 이탈율이 높게 나타남. 영원노래의 숲은 동선이 복잡한 것으로 유명함
* 멀고어 역시 다른 지역으로 이동하는 데 어려운 동선이 있어 이탈율이 높은 것으로 보임

#### 종족 및 직업별 이탈 수준

<p float="left" align="center">
  <img src="/img/race_class_churn.png" alt="race_class_churn" style="zoom:70%;" width="70%"/> 
</p>

* 블러드엘프 종족이 가장 많이 이탈함. 블러드엘프와 도적(rogue), 흑마법사(warlock), 사냥꾼(hunter) 조합의 이탈률이 가장 높음.
* 블러드엘프의 경우 영원노래의 숲에서 게임을 시작하는데 이곳의 퀘스트 동선이 복잡해 이탈율이 높은 것으로 추정됨.
* 그밖에 언데드-도적, 오크-도적, 타우렌-전사(warrior) 조합도 이탈율이 높은 편임.
* 이탈율이 가장 종족은 트롤이며, 전사, 사제(priest), 주술사(shaman)와의 조합에서 이탈율이 낮음.
