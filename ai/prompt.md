# 프롬프트 작성법

## Prompt 작성전에 설정해야 할 것

1. 오른쪽 위에 ChatGPT 맞춤 설정을 누르고, 내용을 입력(인터넷에 예시 내용 많기 때문에 참고해서 입력)

## Prompt 작성법(기본)

1. 미사여구를 많이 넣는게 좋다

- 이전

성능 문제를 해결하는 방법을 알려주세요.

- 이후

현재 프로젝트에서 성능 문제가 발생하여 서비스의 안정성에 영향을 미치고 있습니다.  
이 문제를 해결하기 위한 최적화 방법에 대해 전문가의 조언을 구하고자 합니다.  
성능 개선이 중요한 상황이기 때문에, 실질적인 해결책을 찾고 싶습니다.

2. 원하는 답변이 한번에는 안나오기 때문에, 한채팅에서 계속해서 질문 수정해가면서 해서 답을 좁히고 원하는 답변이 나오면 저장을 함(해당 채팅 옵션에서 이름 바꾸고, 아카이브에 보관, 이후 필요할때마다 사용)

## Prompt 질문법(Skill)

1. 롤플레잉, 역할 나누기(인물, 상황, 목적, 방법)

인물, 상황, 목적, 방법을 넣어서 질문하기

인물은 인공지능에게 역할을 부여하거나 나에 대한 배경 설명중 하나를 하면됨

- 인공지능에게 역할을 부여

  - 예) 너는 전문 투어가이드야

- 나(물어보는 사람)에 대한 배경 설명

  - 예) 나는 한국에서 유럽으로 놀러가고 싶은 대학생이야

- ex1(인물만 가지고)

  - 너는 전문 투어 가이드야. 나는 한국에서 유럽으로 놀러가는 대학생이야. 최고의 유럽여행 스케쥴 한문단으로 만들어줘, let's think step by step

- ex2(인물, 상황, 목적, 방법)

  너는 전문 영화 평론가야.(인물)
  나는 지금 영화 타이타닉에 대한 감상문을 작성해야해.(상황)  
  나는 많은 사람들이 공감할수 있는, 영화의 숨겨진 의미를 해석하고, 다양한 관점에서 영화를 해석하는 감상문을 작성하려고 해.(목적)  
  감상문 처음에는 독자들에게 질문을 던지며 시작하고, 그 질문에 대한 답변을 영화의 내용으로부터 얻을 수 있는 인생의 교훈을 적어줘,  
  그리고 줄거리 소개하는 부분은 생략하고, 독자는 이미 줄거리를 다 알고 있다고 가정하자(방법)

2. 예시(Zero Shot vs Few Shot)

- ZeroShot이란?

챗 GPT에다가 상황설명없이 바로 물어보는걸 뜻함

- Few Shot

예시를 줘서 문맥을 이해시켜 더 나은 답변을 제시하도록 지시하는 것

예시를 넣어줘서 응답을 유도하는 기술, 예시가 많을 수록 좋음,  
블로그를 쓸때 내가 잘썼다고 생각하는 글이 있거나 하면 그걸 가져와서 예시로 주면 비슷하게 써준다던지 활용 가능  
많으면 많을수록 좋음

- ex1

  1. 나는 오후에
  2. 나는 아침에 토스트를 먹은 뒤 지하철을 타고 학교에 갔다. 나는 오후에
     =>
     1을 할때와 2를 할때의 차이는 2번은 앞의 예시를 보고 일기장이라는 것을 추론해서 응답을 줌

- ex2
  1. 유럽 => 유럽에 대한 설명을 해줄꺼임(Zero shot)
  2. Q: "동남아시아"  
     A: "싱가포르의 미래적인 도시 경관 감상 후 말레이시아 쿠알라룸푸르의 페트로나스 트윈 타워를 거쳐 태국 방콕의 화려한 왕궁과 시장을 탐방하고, 마지막으로 베트남 하노이의 구시가지와 할롱베이의자연 경관을 즐기는 여정"  
     Q: "유럽"  
     A:  
     => 이렇게 내용을 질문하면 여행에 관련된 유럽의 내용을 대답해줌

3. 추론시키기(Chain of Thoughts)

- 챗GTP는 언어 기반 인공지능 모델

  - 사람들이 만든 텍스트 기반
  - 정확한 답을 구사하기보다는 "그럴싸한" 답을 내놓는다
  - ChatGPT는 추론에 약함(어려운 연산이나 수학문제같은거), 언어기반 모델이라 텍스트기반으로 추론하기 때문에(현재는 많이 개선되긴함)

- 강제로 생각을 말하면서(Chain of Thoughts)
  - 추론을 하게끔 유도하면, 그 오류를 줄일수 있다

단계별로 생각해봐(Let's think step by step)라는 텍스트를 마지막에 추가함으로써, 사람과 같이 단계별로 생각해서 추론

- ex1
  한 질병에 걸릴 확률은 1%입니다. 특정 검사는 이 질병을 진단할 때 다음과 같은 특성을 지닙니다:  
  실제로 질병이 있는 사람을 양성으로 판별할 확률(민감도): 95%  
  실제로 질병이 없는 사람을 음성으로 판별할 확률(특이도): 90%  
  임의의 사람이 검사에서 양성을 받을 확률을 얼마인가요?

  그리고, 한 사람이 양성 판정을 받았을 때, 실제로 질병에 걸렸을 확률은 얼마인가요?

  단계별로 생각해봐

4. 인간취급

ChatGPT를 사람처럼 대하고, 칭찬을 많이 하거나 하면 답변의 퀄리티가 높아짐

- 이름 불러주기

  - ex) 너는 전문가이드 알렉스야

- 반복적으로 말해서 강조하기

  - ex) 너는 최고의 전문가니까

- 반드시 가장 좋은 답을 내라고 말하기

  - ex) 세상에서 가장 좋은 계획을 세워줘

- 중요한 정보 알려주기

  - ex) 너무 힘든 여행은 아니길 바래

- 칭찬해주기

  - ex) 넌 정말 잘 할 수 있어

- ex)  
  "너는 최고의 전문 투어가이드 '알렉스야'.  
  너는 한국에서 유럽으로 놀러가는 대학생이야.  
  최고의 '유럽' 여행 스케줄 한문단으로 만들어줘.  
  너무 현란한 여행은 아니길 바래.  
  너는 최고의 전문 가이드니까, 세상에서 가장 좋은 계획을 만들어 줄 수 있어.  
  너는 꼭 잘해낼거야
  Let's this step by step
