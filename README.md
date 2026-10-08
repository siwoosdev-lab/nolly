# nolly

널리(Nolly) 앱들의 공개 안내 사이트. GitHub Pages 로 서비스된다.

App Store Connect·Play Console 은 개인정보처리방침·지원·계정 삭제 페이지를
**로그인 없이 열리는 공개 URL** 로 요구하는데, 앱 소스 저장소는 비공개라
Pages 를 쓸 수 없어 이 저장소를 따로 둔다.

## 구조

```
index.html          앱 목록 (손으로 관리)
gyeongjosa/         경조사관리 — 생성물, 직접 고치지 말 것
```

## 경조사관리 페이지를 고치려면

`gyeongjosa/` 아래 HTML 은 **앱 안 문구(`lib/core/l10n/app_strings.dart` 의
`privacyPolicyBody` · `termsOfServiceBody`)에서 생성된다.** 웹만 고치면 앱 안
고지와 갈라지고, 갈라진 고지는 그 자체가 위반이다. 반드시 앱 저장소에서:

```sh
cd <경조사관리 저장소>
python3 tool/build_legal_site.py        # 기본 출력: ../nolly-site/gyeongjosa
cd ../nolly-site && git add -A && git commit && git push
```
