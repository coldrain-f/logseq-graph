# 📚 Logseq Graph

이 저장소는 개인적인 지식 관리와 디지털 노트를 위한 Logseq graph입니다.

## 🔧 설정 방법

1. [Logseq](https://logseq.com/)을 설치합니다
2. 이 저장소를 클론합니다:
   ```bash
   git clone https://github.com/coldrain-f/logseq-graph.git
   ```
3. Logseq을 실행하고 Open folder as a graph에서 클론한 폴더를 선택합니다

## 🔄 동기화

이 graph는 Git을 통해 관리되며, Logseq의 기본 Git 기능을 사용해 자동으로 동기화됩니다.

### Git 동기화 설정
1. Logseq 설정에서 Git 자동 백업 활성화
2. Git 저장소 연결 확인
3. 자동 백업 주기 설정

## ⚠️ 주의사항

- 민감한 정보는 커밋하지 말기
- `.gitignore`에 명시된 파일/폴더는 동기화에서 제외됨
- `logseq/bak` 폴더는 자동 백업 파일 포함
- `/logseq` 폴더는 Logseq 설정 파일을 포함하고 있음

## 🗂 기본 파일 구조

```
.
├── /journals   # 일간 노트
├── /pages      # 일반 노트
├── /assets     # 이미지 등 첨부 파일
└── /logseq     # 설정 파일
```

## 📝 라이선스 / License

개인 사용 목적으로 생성된 graph입니다. 무단 복제 및 배포를 금지합니다.

This graph is created for personal use only. Unauthorized copying and distribution are prohibited.
