# Tamamon for Windows — 릴리스

Windows용 픽셀아트 데스크탑 펫의 **배포 채널**입니다. Claude Code로 코딩할수록
알이 자라 부화하고, 어른·진화까지 성장합니다.

제품 소개와 macOS판은 [tamamons.com](https://tamamons.com) 에 있습니다.

macOS 판([`tamamons-release`](https://github.com/besslframework-stack/tamamons-release))과
채널을 분리한 이유는 버전 궤도가 독립적이기 때문입니다. 앱이 상대 플랫폼의 태그를
잘못 읽어 오작동할 여지가 없습니다.

## 다운로드

[최신 릴리스](../../releases/latest)에서 받으세요.

| 파일 | 언제 |
|---|---|
| `Tamamon-Setup.exe` | 보통은 이것. 시작 프로그램 등록·바로가기·제거 프로그램 포함 |
| `Tamamon-portable.zip` | 설치 없이 쓰고 싶을 때. 압축을 풀고 `Tamamon.exe` 실행 |

파일 이름에 버전을 넣지 않습니다. 그래야 아래 주소가 항상 최신을 가리킵니다.

```
https://github.com/besslframework-stack/tamamon-windows-release/releases/latest/download/Tamamon-Setup.exe
```

**요구 사항**: Windows 10 (2004 이상) 또는 11 · 64비트.

## 무서명 배포

코드 서명 인증서가 없어 **"Windows에서 PC를 보호했습니다" 경고가 뜹니다.**
[추가 정보] → [실행] 을 누르시면 됩니다.

숨기지 않고 먼저 말하는 편이 낫다고 판단했습니다. 대신 확인할 수단을 드립니다 —
각 릴리스에 `SHA256SUMS.txt` 가 함께 올라갑니다.

```powershell
Get-FileHash .\Tamamon-Setup.exe -Algorithm SHA256
```

## 무엇을 보내고 무엇을 안 보내는가

Tamamon 은 로컬에서 동작합니다. 코드도 대화 내용도 보내지 않습니다.
나가는 통신은 두 곳뿐입니다.

- `api.anthropic.com` — 사용량 계기판 조회 (세션·주간 %)
- `api.github.com` — 새 버전 확인

날씨용 외부 API 는 배포본에서 **차단**되어 있고, 배포본에서는 환경변수로도 열 수
없습니다. 빌드 게이트가 매번 그 사실을 확인합니다.

## 문제가 생기면

트레이 → 고급 → **문제 진단**을 열어 내용을 복사해 보내주세요.
경로·세션 내용·로그는 담기지 않습니다 — 무엇이 담기는지 복사 전에 화면에서
그대로 보여드립니다.

[이슈 남기기](../../issues)
