# Pixel Universe (원밀리언달러픽셀)

1,000×1,000 픽셀 디지털 광고판 — SEO 백링크 & AEO 인용 효과 제공

## 파일 구조

```
index.html          ← 메인 페이지 (픽셀 그리드 + 랜딩 섹션)
ads.json            ← 광고주 데이터 (여기만 수정하면 됨)
advertiser/
  index.html        ← 광고주 서브페이지 템플릿 (공통)
images/
  README.md         ← 이미지 관리 가이드
  (광고주id).png    ← 광고주 로고 이미지
```

## 광고주 추가 방법

`ads.json` 에 객체 하나 추가 후 커밋하면 끝입니다.
HTML 파일은 건드리지 않아도 됩니다.

```json
{
  "id": "브랜드-영문",
  "bx": 0,
  "by": 0,
  "bw": 10,
  "bh": 10,
  "color": "#ff2d9b",
  "label": "브랜드\n이름",
  "img": null,
  "url": "https://브랜드사이트.com",
  "title": "브랜드명 — 업종 설명",
  "keywords": "브랜드명 업종 키워드 — SEO 앵커 텍스트",
  "name": "Brand Name",
  "nameKo": "브랜드명",
  "location": "City, Country",
  "locationKo": "위치 한국어",
  "tagline": "English tagline",
  "taglineKo": "한국어 태그라인",
  "description": "브랜드 소개 문장.",
  "services": ["서비스1", "서비스2"],
  "diveSites": [],
  "features": ["특징1", "특징2"],
  "contact": {
    "phone": "010-0000-0000",
    "kakao": "",
    "email": ""
  },
  "accentColor": "#ff2d9b",
  "pixelX": 0,
  "pixelY": 0,
  "pixelW": 100,
  "pixelH": 100,
  "startDate": "YYYY-MM-DD"
}
```

## 수정이 필요한 설정값

`index.html` 상단 `<script>` 블록에서 아래 두 값을 교체하세요.

```js
const GOOGLE_FORM_URL = 'https://forms.gle/실제URL';
const INDEXNOW_KEY    = '실제키값';
const SITE_URL        = 'https://실제도메인.com/';
```

`<head>` 의 메타태그에서도 도메인을 교체하세요.

```html
<link rel="canonical" href="https://실제도메인.com/">
<meta property="og:url" content="https://실제도메인.com/">
```

## 광고주 서브페이지 URL

```
https://도메인.com/advertiser/index.html?id=광고주id
```

예시:
- https://도메인.com/advertiser/index.html?id=amigo-dive
- https://도메인.com/advertiser/index.html?id=bubble-tank

## GitHub Pages 배포

1. 이 레포를 GitHub에 push
2. Settings → Pages → Branch: main / (root) → Save
3. 도메인 연결: Settings → Pages → Custom domain 입력

## 로컬 테스트 주의사항

`file://` 로 직접 열면 `ads.json` fetch가 CORS 오류로 실패합니다.
로컬 테스트는 VS Code Live Server 또는 아래 명령어를 사용하세요.

```bash
python -m http.server 8080
# 브라우저에서 http://localhost:8080 접속
```
