# AX Seminar Archive

AX 세미나 발표자료를 보관하고, 현재 발표할 자료를 GitHub Pages로 서빙하는 저장소입니다.

## 접속 주소

- Pages: <https://dsseo-whereable.github.io/ax-seminar/>
- Repository: <https://github.com/dsseo-whereable/ax-seminar>

## 구조

- `index.html`: archive 목록과 발표자료 viewer를 제공하는 Pages 메인 화면
- `archive/`: 날짜별 발표자료 HTML 보관 위치
- `archive/manifest.json`: 메인 화면에 표시할 발표자료 목록
- `PUBLISHING.md`: 새 발표자료 추가 및 배포 절차

## 운영 방식

새 발표자료는 `archive/YYYYMMDD.html`로 추가하고 `archive/manifest.json`에 등록합니다.

`index.html`은 발표자료 파일로 덮어쓰지 않고, archive viewer 역할로 유지합니다.
