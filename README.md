# CodeUpdater

[🇺🇸English](README.md) | [🇰🇷한국어](README_ko.md)

**CodeUpdater** is a Python-based tool designed to automate the process of updating, inserting, or deleting lines in multiple files within a project directory based on a specified JSON configuration.

## Features

- **Update**: Replace specific lines in a file with new content.
- **Insert**: Insert new lines at a specific position in a file.
- **Delete**: Remove specific lines from a file.

## Installation

Clone the repository to your local machine:

```bash
git clone https://github.com/joonheeu/code-updater.git
cd code-updater
```

## Usage

To use `CodeUpdater`, ensure that you have Python installed. Then, create an `updates.json` file in the root directory of your project, and structure it according to the following example:

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

Run the script using the following command:

```bash
python main.py {project_root_path}
```

Replace `{project_root_path}` with the root directory of your project where the files are located.

## Logging

The tool generates logs in the `logs/` directory inside the specified project root. Each log file is timestamped and details the changes made to the files.

## Contributing

Contributions are welcome! Please fork the repository and submit a pull request.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contact

**Author:** Daniel  
**Email:** [daniel@udit.one](mailto:daniel@udit.one)  
**Company:** UDIT