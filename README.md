# Sic Bo (다이사이)

브라우저에서 플레이하는 카지노 다이사이(Sic Bo) 아케이드 SPA입니다.  
**빌드 도구 없이** `index.html` 하나로 동작하며, Vercel 정적 호스팅에 바로 배포할 수 있습니다.

## 파일 구조

```
.
├── index.html      # 게임 UI + 룰 + 오디오 + 히스토리 (단일 SPA)
├── vercel.json     # 정적 사이트 라우팅 / 헤더
└── README.md
```

## 로컬 실행

정적 서버로 루트를 열면 됩니다.

```bash
npx --yes serve .
# 또는
python3 -m http.server 3000
```

브라우저에서 `http://localhost:3000` (또는 안내된 포트)로 접속하세요.

## Vercel 배포

1. 이 저장소를 [Vercel](https://vercel.com)에 Import
2. **Framework Preset**: Other (또는 정적 사이트)
3. **Build Command**: 비워 둠 (빌드 없음)
4. **Output Directory**: `.` (프로젝트 루트)
5. Deploy

`vercel.json`이 SPA 정적 라우팅과 기본 보안 헤더를 설정합니다.  
CLI를 쓸 경우:

```bash
npx vercel --yes
```

## 게임 기능

- 베팅: Big/Small, Odd/Even, 합계 4–17, Specific/Any Triple
- 칩 단위 10 / 50 / 100 / 500 · Clear · Rebet
- ~1.8초 쉐이커 + 주사위 tumble 애니메이션 (CSS pip 눈금)
- 표준 배당 정산 (트리플 시 대/소·홀/짝은 하우스 승)
- 당첨 구역 glow, 승리 토스트 / 플로팅 `+금액`
- Web Audio API 합성음 (칩 / 주사위 / 승리 아르페지오) — 외부 파일 없음
- 최근 10회 Roadmap 히스토리
- 파산 시 **무료 충전 (Recharge)** 1,000칩

## 기술 스택

- HTML5 · Vanilla JavaScript · Tailwind CSS (CDN)
