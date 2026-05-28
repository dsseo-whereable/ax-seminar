# Publishing Procedure

## 새 발표자료 게시

1. 새 발표자료 HTML 파일 이름을 날짜로 정한다.

   예: `20260601.html`

2. 파일을 `archive/`에 복사한다.

   ```bash
   cp /path/to/20260601.html archive/20260601.html
   ```

3. `archive/manifest.json`에 새 항목을 추가한다.

   ```json
   {
     "id": "20260601",
     "title": "Presentation Title",
     "date": "2026-06-01",
     "path": "archive/20260601.html",
     "summary": "Short archive label.",
     "current": true
   }
   ```

4. 기존 항목의 `"current": true`는 제거하거나 `false`로 바꾼다.

5. `index.html`은 발표자료로 덮어쓰지 않는다.

## 로컬 확인

```bash
python3 -m http.server 8765 --bind 127.0.0.1
```

브라우저에서 확인한다.

```text
http://127.0.0.1:8765/
```

확인할 것:

- 첫 화면에서 최신 발표자료가 보인다.
- 사이드바 버튼을 누르면 archive 목록이 열린다.
- 새 발표자료를 선택하면 iframe에 표시된다.

## 배포

```bash
git add archive/20260601.html archive/manifest.json
git commit \
  -m "Publish the 20260601 seminar" \
  -m "The seminar archive receives the dated HTML file and marks it as the current presentation in the manifest." \
  -m "Constraint: index.html remains the archive launcher" \
  -m "Confidence: high" \
  -m "Scope-risk: narrow" \
  -m "Tested: Verified local archive launcher and direct deck URL" \
  -m "Co-authored-by: OmX <omx@oh-my-codex.dev>"
git push
```

## 배포 확인

```bash
curl -L https://dsseo-whereable.github.io/ax-seminar/
curl -L https://dsseo-whereable.github.io/ax-seminar/archive/20260601.html
```

확인할 것:

- root URL에서 archive launcher가 열린다.
- 새 발표자료 URL이 HTTP 200으로 응답한다.
