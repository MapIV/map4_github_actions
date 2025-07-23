# map4_github_actions

C/C++のフォーマットには `clang-format-18` を利用している

## Usage

### C/C++ Formatter

CIでテストしたいレポジトリのCI設定に次のように追加する。トリガーなどは各自の要件に合わせる。

```yaml

name: Formatter CI

on:
  pull_request

jobs:
  call-formatter:
    uses: MapIV/map4_github_actions/.github/workflows/formatter.yml@v2025.07.23
    secrets:
      REPO_TOKEN: ${{ secrets.GITHUB_TOKEN }}
      CI_USER_APP_ID: ${{ secrets.CI_USER_APP_ID }}
      CI_USER_PRIVATE_KEY: ${{ secrets.CI_USER_PRIVATE_KEY }}

```

### Pre-commit Formatter

利用したいレポジトリのルートに`.pre-commit-config.yaml`を配置する。
