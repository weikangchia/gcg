# Git Changelog Generator

**gitcg** is a customizable changelog generator for GitLab using milestone.

## Getting Started

### Pre-requisites

- Install [node](https://nodejs.org/en/download/)
- Install gitcg
  ```
  npm install -g gitcg
  ```

### GitLab

- Get a personal token (scopes: `read_api`)
- Store it as a environment variable
  ```export GITLAB_TOKEN=<your personal gitlab token>```

### Usage
```sh-session
USAGE:
    gitcg

OPTIONS:
    -m, --milestone=milestone        title of milestone
    -p, --projectPath=projectPath    path to project
    --config=config                  custom config file name (default is config.json)
```

**Examples**
```
gitcg -m "Milestone 1" -p "khubite/test"
```

## Configuration Options

By default **gitcg** reads all configurable options from `config.json` at the following location

```
Unix: ~/.config/gitcg
Windows: %LOCALAPPDATA%\gitcg
Can be overridden with XDG_CONFIG_HOME
```

 Below are the available configurable options.

- [service](#service)
- [serviceUrl](#serviceUrl)
- [sections](#sections)
  - [title](#title)
  - [labels](#labels)
- [enableContributorsSection](#enableContributorsSection)
- [contributorsToExclude](#contributorsToExclude)
- [contributorTitle](#contributorTitle)
- [enableExternalIssuesTracker](#enableExternalIssuesTracker)
- [externalIssuesUrl](#externalIssuesUrl)
- [externalIssuesProjects](#externalIssuesProjects)
- [enableCommitSha](#enableCommitSha)

### service

| Name        | Value           |
| ------------- |-------------|
| type      | string |
| mandatory | true |
| supportedValues | gitlab |


Example
```json
{
  "service": "gitlab"
}
```

### serviceUrl

| Name        | Value           |
| ------------- |-------------|
| type      | string |
| mandatory | true |

Example
```json
{
  "service": "gitlab",
  "serviceUrl": "https://gitlab.com"
}
```

### sections

| Name        | Value           |
| ------------- |-------------|
| type      | array |
| mandatory | false |

Example
```json
{
  "service": "gitlab",
  "serviceUrl": "https://gitlab.com",
  "sections": []
}
```

#### title

| Name        | Value           |
| ------------- |-------------|
| type      | string |
| parent    | sections |
| mandatory | true |

Example
```json
{
  "service": "gitlab",
  "serviceUrl": "https://gitlab.com",
  "sections": [
    {
      "title": ":star2: New Features",
      "labels": ["feature"]
    }
  ]
}
```

#### labels

| Name        | Value           |
| ------------- |-------------|
| type      | string |
| parent    | sections |
| mandatory | true |

Example
```json
{
  "service": "gitlab",
  "serviceUrl": "https://gitlab.com",
  "sections": [
    {
      "title": ":star2: New Features",
      "labels": ["feature"]
    }
  ]
}
```

### enableContributorsSection

| Name        | Value           |
| ------------- |-------------|
| type      | boolean |
| mandatory | false |

Example
```json
{
  "service": "gitlab",
  "serviceUrl": "https://gitlab.com",
  "enableContributorsSection": true,
  "contributorTitle": ":heart: Contributors\nWe'd like to thank all the contributors who worked on this sprint!"
}
```

### contributorsToExclude

| Name        | Value           |
| ------------- |-------------|
| type      | array |
| mandatory | false |

Example
```json
{
  "service": "gitlab",
  "serviceUrl": "https://gitlab.com",
  "enableContributorsSection": true,
  "contributorsToExclude": ["user1", "user2"],
}
```

### contributorTitle

| Name        | Value           |
| ------------- |-------------|
| type      | string |
| mandatory | false |

Example
```json
{
  "service": "gitlab",
  "serviceUrl": "https://gitlab.com",
  "enableContributorsSection": true,
  "contributorTitle": ":heart: Contributors\nWe'd like to thank all the contributors who worked on this sprint!"
}
```

### enableExternalIssuesTracker

| Name        | Value           |
| ------------- |-------------|
| type      | array |
| mandatory | false |

Example
```json
{
  "service": "gitlab",
  "serviceUrl": "https://gitlab.com",
  "enableExternalIssuesTracker": true
}
```

### externalIssuesUrl

| Name        | Value           |
| ------------- |-------------|
| type      | string |
| mandatory | false |

Example
```json
{
  "service": "gitlab",
  "serviceUrl": "https://gitlab.com",
  "enableExternalIssuesTracker": true,
  "externalIssuesUrl": "https://youtrack.com/issue",
}
```

### externalIssuesProjects

| Name        | Value           |
| ------------- |-------------|
| type      | array |
| mandatory | false |

Example
```json
{
  "service": "gitlab",
  "serviceUrl": "https://gitlab.com",
  "enableExternalIssuesTracker": true,
  "externalIssuesUrl": "https://youtrack.com/issue",
  "externalIssuesProjects": ["PROJ1", "PROJ2"],
}
```

### enableCommitSha

| Name        | Value           |
| ------------- |-------------|
| type      | boolean |
| mandatory | false |

Example
```json
{
  "service": "gitlab",
  "serviceUrl": "https://gitlab.com",
  "enableCommitSha": true
}
```

## License

Distributed under the MIT License. See [LICENSE](license) for more information.

## Contributing
Contributions are what make the open source community such an amazing place to be learn, inspire, and create. Any contributions you make are greatly appreciated.

## Contact

Wei Kang - weikangchia@gmail.com
