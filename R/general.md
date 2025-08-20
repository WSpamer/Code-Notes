# General

## 1) Git

Link: <https://happygitwithr.com/>

### 1.1) Generate Token

### Browser

1. Go to: <https://github.com/settings/tokens>
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
<https://code.visualstudio.com/docs/languages/r>

## Radian

Link:
<https://github.com/randy3k/radian>

## Python in R

Package: reticulate
Link: <https://cran.r-project.org/web/packages/reticulate/vignettes/calling_python.html>

## 3) Global packages

```R
   install.packages("renv")
   install.packages("devtools")
   devtools::install_github("rstudio/addinexamples", type = "source")

```

## Promising Packages

[simET](https://cran.r-project.org/web/packages/simET/simET.pdf)

## Misc

[Using RStudio Server in Windows WSL2](https://support.posit.co/hc/en-us/articles/360049776974-Using-RStudio-Server-in-Windows-WSL2)
[Python in R](https://rstudio.github.io/reticulate/)
[R Web API](https://www.rplumber.io/)
