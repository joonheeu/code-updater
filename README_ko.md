# CodeUpdater

[🇺🇸English](README.md) | [🇰🇷한국어](README_ko.md)

**CodeUpdater**는 지정된 JSON 설정에 따라 프로젝트 디렉토리 내 여러 파일의 특정 라인을 업데이트, 삽입 또는 삭제하는 작업을 자동화하기 위해 설계된 Python 기반 도구입니다.

## 기능

- **업데이트**: 파일의 특정 라인을 새 내용으로 대체합니다.
- **삽입**: 파일의 특정 위치에 새 라인을 삽입합니다.
- **삭제**: 파일의 특정 라인을 삭제합니다.

## 설치

리포지토리를 로컬 컴퓨터에 클론합니다:

```bash
git clone https://github.com/joonheeu/code-updater.git
cd code-updater
```

## 사용법

`CodeUpdater`를 사용하려면 Python이 설치되어 있어야 합니다. 그런 다음 프로젝트의 루트 디렉토리에 `updates.json` 파일을 생성하고, 다음 예시와 같이 구조를 설정합니다:

```json
[
  {
    "path": "src/test.py",
    "line": 42,
    "type": "update",
    "replace": [
      "new line 42 content",
      "new line 43 content",
      "new line 44 content",
      "new line 45 content"
    ]
  }
]
```

다음 명령어를 사용하여 스크립트를 실행합니다:

```bash
python main.py {project_root_path}
```

여기서 `{project_root_path}`는 파일이 위치한 프로젝트의 루트 디렉토리로 대체해야 합니다.

## 로그

이 도구는 지정된 프로젝트 루트 내부의 `logs/` 디렉토리에 로그 파일을 생성합니다. 각 로그 파일에는 타임스탬프가 찍히며, 파일에 적용된 변경 사항이 기록됩니다.

## 기여

기여를 환영합니다! 리포지토리를 포크하고 풀 리퀘스트를 제출해 주세요.

## 라이선스

이 프로젝트는 MIT 라이선스에 따라 라이선스가 부여됩니다. 자세한 내용은 [LICENSE](LICENSE) 파일을 참조하세요.

## 연락처

**작성자:** Daniel  
**이메일:** [daniel@udit.one](mailto:daniel@udit.one)  
**회사:** UDIT