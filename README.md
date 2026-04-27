# yh-calendar — 양홍수 변호사 촬영·업로드 일정

## 이게 뭔가요?

양변/경민PD/대표님한테 공유하는 촬영·업로드 일정표입니다.
URL 하나 보내면 누구나 로그인 없이 볼 수 있습니다.

## 파일 구조 (2개만 알면 됨)

```
yh-calendar/
├── index.html       ← 달력 화면 (안 건드림)
├── schedule.json    ← 일정 데이터 (이것만 수정)
├── README.md        ← 지금 보고 있는 이 파일
└── .gitignore
```

## 일정 추가/수정 방법

1. Claude한테 채팅으로 말함
   - "5월 12일 세금 체납 영상 촬영 추가해줘"
   - "EP01 촬영 완료 처리해줘"
   - "EP02 편집일 5/10으로 변경해줘"

2. Claude가 schedule.json 수정 → 깃 푸시

3. 사이트 자동 반영 (1~2분)

**김PD님은 코드 안 봅니다.**

## 최초 셋업 (한 번만)

### 1단계: 이 폴더에서 깃 시작

```bash
cd C:\Users\(본인경로)\yh-calendar
git init
git add .
git commit -m "init: yh-calendar"
```

✅ 정상이면 `create mode 100644 index.html` 같은 줄이 뜸

### 2단계: GitHub에 레포 만들기

1. https://github.com/new 접속
2. Repository name: `yh-calendar`
3. Public 선택 (Vercel 무료 배포용)
4. **Create repository** 클릭
5. 뜨는 화면에서 "…or push an existing repository" 아래 명령어 복붙:

```bash
git remote add origin https://github.com/(본인계정)/yh-calendar.git
git branch -M main
git push -u origin main
```

### 3단계: Vercel에 배포

1. https://vercel.com/new 접속
2. Import Git Repository → 방금 만든 `yh-calendar` 선택
3. **Deploy** 클릭
4. 끝. URL 나옴 (예: `yh-calendar.vercel.app`)

### 4단계: 공유

카톡/슬랙에 URL 던지면 끝.
양변/경민PD/대표님 누구나 브라우저에서 바로 볼 수 있음.

## JSON 수정 후 반영

```bash
cd C:\Users\(본인경로)\yh-calendar
git add schedule.json
git commit -m "일정 업데이트"
git push
```

Vercel이 자동으로 재배포합니다. 1~2분 후 사이트 새로고침하면 반영.

## 문제가 생기면

에러 메시지 그대로 캡처해서 Claude한테 던지세요.
