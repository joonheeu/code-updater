# CodeUpdater

[🇺🇸English](README.md) | [🇰🇷한국어](README_ko.md)

**CodeUpdater**는 지정된 JSON 설정에 따라 프로젝트 디렉토리 내 여러 파일의 특정 라인을 업데이트, 삽입 또는 삭제하는 작업을 자동화하기 위해 설계된 Python 기반 도구입니다.

## 목차

- [기능](#기능)
- [설치](#설치)
- [사용법](#사용법)
- [JSON 설정](#json-설정)
- [예제](#예제)
- [로그](#로그)
- [기여](#기여)
- [라이선스](#라이선스)
- [연락처](#연락처)

## 기능

- **업데이트**: 파일의 특정 라인을 새 내용으로 대체합니다.
- **삽입**: 파일의 특정 위치에 새 라인을 삽입하며, 기존 라인은 아래로 밀려납니다.
- **삭제**: 파일의 특정 라인을 삭제합니다.

## 설치

CodeUpdater를 설치하려면 `pip`을 사용하세요. 다음 명령어를 실행합니다:

```bash
pip install code-updater
```

또는, 로컬 복사본에서 설치하려면 다음 단계를 따르세요:

1. 리포지토리를 로컬 컴퓨터에 클론합니다:

   ```bash
   git clone https://github.com/joonheeu/code-updater.git
   cd code-updater
   ```

2. 패키지를 로컬에 설치합니다:

   ```bash
   pip install .
   ```

## 사용법

`CodeUpdater`를 사용하려면 Python이 설치되어 있어야 합니다. 그런 다음 프로젝트의 루트 디렉토리에 `updates.json` 파일을 생성하고, 아래 설명된 설정에 따라 구조화하세요.

스크립트를 실행하려면 다음 명령어를 사용합니다:

```bash
cup [OPTIONS] {project_root_path}
```

여기서 `{project_root_path}`는 파일이 위치한 프로젝트의 루트 디렉토리로 대체해야 합니다.

### 옵션

- `-h`, `--help`: 도움말 메시지를 출력하고 종료합니다.
- `-V`, `--version`: 현재 버전을 출력하고 종료합니다.

## JSON 설정

JSON 파일은 수행할 작업을 설명해야 합니다. JSON 파일의 구조는 다음과 같습니다:

```json
[
  {
    "path": "src/example.py",
    "line": 42,
    "type": "update",  # 작업 유형: "update", "insert", 또는 "delete"
    "replace": [
      "new line 42 content",
      "new line 43 content"
    ]
  }
]
```

### 타입

- **update**: 지정된 라인 번호에서 시작하여 "replace" 리스트에 제공된 내용으로 해당 라인을 대체합니다.
- **insert**: 지정된 라인 번호에서 "replace" 리스트의 내용을 삽입하며, 기존 라인은 아래로 밀려납니다.
- **delete**: 지정된 라인을 삭제합니다. 이 작업에서는 "replace" 필드가 필요하지 않습니다.

### 예제

다음은 설정 예제입니다:

```json
[
  {
    "path": "src/example.py",
    "line": 42,
    "type": "update",
    "replace": [
      "updated line 42 content",
      "updated line 43 content"
    ]
  },
  {
    "path": "src/example.py",
    "line": 10,
    "type": "insert",
    "replace": [
      "inserted line 10 content",
      "inserted line 11 content"
    ]
  },
  {
    "path": "src/example.py",
    "line": 15,
    "type": "delete"
  }
]
```

이 예제에서:
- `src/example.py`의 42번 라인과 43번 라인이 업데이트됩니다.
- 10번 라인에 새 내용이 삽입되고, 기존 라인은 아래로 이동됩니다.
- 15번 라인이 삭제됩니다.

## 로그

이 도구는 지정된 프로젝트 루트 내부의 `logs/` 디렉토리에 로그 파일을 생성합니다. 각 로그 파일에는 타임스탬프가 찍히며, 파일에 적용된 변경 사항이 기록됩니다. 로그에는 비교를 위해 원본 및 업데이트된 내용이 모두 포함됩니다.

## 기여

기여를 환영합니다! 리포지토리를 포크하고 풀 리퀘스트를 제출해 주세요. 문제가 있거나 제안 사항이 있는 경우, GitHub에서 이슈를 열어 주세요.

## 라이선스

이 프로젝트는 MIT 라이선스에 따라 라이선스가 부여됩니다. 자세한 내용은 [LICENSE](LICENSE) 파일을 참조하세요.

## 연락처

**작성자:** Daniel  
**이메일:** [daniel@udit.one](mailto:daniel@udit.one)  
**회사:** UDIT

자세한 내용은 GitHub 리포지토리에서 확인하세요: [CodeUpdater](https://github.com/joonheeu/code-updater)