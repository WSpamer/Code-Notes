# General

## 1) Git

Link: https://happygitwithr.com/

### 1.1) Generate Token

### Browser

1. Go to: https://github.com/settings/tokens
2. Select Token (Classic)

### R

#### Initialize

    ```
    # Initialize
    renv::init()
    install.packages("usethis")
    # Create Token
    usethis::create_github_token()
    # Copy Result
    gitcreds::gitcreds_set()
    # Paste Result
    ```

#### Create Token

usethis::create_github_token()

## 2) VS Code

Link:
https://code.visualstudio.com/docs/languages/r

#### Radian

Link:
https://github.com/randy3k/radian
