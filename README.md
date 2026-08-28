# Tamamon for Windows — 릴리스

Windows용 픽셀아트 데스크탑 펫의 **배포 채널**입니다. 소스는 여기 없습니다 —
[`tamamon-windows`](https://github.com/besslframework-stack/tamamon-windows) 에 있습니다.

macOS 판([`tamamons-release`](https://github.com/besslframework-stack/tamamons-release))과
채널을 분리한 이유는 버전 궤도가 독립적이기 때문입니다. Windows 가 0.9.x 베타를 도는
동안 macOS 는 1.0.x 를 유지할 수 있고, 앱이 상대 플랫폼의 태그를 잘못 읽어 오작동할
여지가 없습니다.

## 다운로드

[Releases](../../releases) 에서 받으세요.

| 파일 | 언제 |
|---|---|
| `Tamamon-Setup-x.y.z.exe` | 보통은 이것. 시작 프로그램 등록·바로가기·제거 프로그램 포함 |
| `Tamamon-x.y.z-portable.zip` | 설치 없이 쓰고 싶을 때. 압축을 풀고 `Tamamon.exe` 실행 |

## 무서명 배포

코드 서명 인증서가 없어 **"Windows에서 PC를 보호했습니다" 경고가 뜹니다.**
[추가 정보] → [실행] 을 누르시면 됩니다.

숨기지 않고 먼저 말하는 편이 낫다고 판단했습니다. 대신 확인할 수단을 드립니다 —
각 릴리스에 `SHA256SUMS.txt` 가 함께 올라갑니다.

```powershell
Get-FileHash .\Tamamon-Setup-0.9.0.exe -Algorithm SHA256
```

## 무엇을 보내고 무엇을 안 보내는가

Tamamon 은 로컬에서 동작합니다. 코드도 대화 내용도 보내지 않습니다.
나가는 통신은 두 곳뿐입니다.

- `api.anthropic.com` — 사용량 계기판 조회 (세션·주간 %)
- `api.github.com` — 새 버전 확인

날씨용 외부 API 는 배포본에서 **차단**되어 있고, 그 사실을 빌드 게이트가 매번 확인합니다.
