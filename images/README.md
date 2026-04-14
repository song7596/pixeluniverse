# images/

광고주 이미지 파일을 이 폴더에 저장합니다.

## 파일 명명 규칙
광고주 id와 동일하게 사용합니다.

예시:
- amigo-dive.png
- bubble-tank.png

## 권장 규격
- 형식: PNG (투명 배경 권장)
- 크기: 픽셀 블록 크기의 배수 (예: 180×140, 200×160)
- 용량: 500KB 이하

## ads.json 연결 방법
이미지를 이 폴더에 넣은 후 ads.json의 해당 광고주 img 필드에 경로를 입력합니다.

```json
{
  "id": "amigo-dive",
  "img": "images/amigo-dive.png",
  ...
}
```

img 필드가 null이면 color + label 텍스트로 표시됩니다.
