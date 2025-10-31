# Packages

## uv

<https://stackoverflow.com/questions/79533324/how-to-install-a-local-package-with-uv>
<https://www.reddit.com/r/learnpython/comments/1ftd6y2/has_anyone_used_uv_with_local_package_dependency/>
<https://docs.astral.sh/uv/guides/package/#publishing-your-package>
[Building and Publishing Packages](https://realpython.com/python-uv/)

## Setup Tools

<https://setuptools.pypa.io/en/latest/userguide/quickstart.html>
<https://docs.python.org/3/library/site.html>
<https://packaging.python.org/en/latest/guides/section-install/>
<https://stackoverflow.com/questions/6956690/best-practice-for-reusing-python-code>
<https://build.pypa.io/en/latest/installation.html>

## Success Comments

<https://sarahglasmacher.com/how-to-build-python-package-uv/>

```bash
# "/home/wspamer/dev/python/packages/nviro_fetch"
# uv add --editable "/home/wspamer/dev/python/packages/nviro_fetch"
# uv pip install -e add "/home/wspamer/dev/python/packages/nviro_fetch"
# uv run --with nviro_fetch --no-project -- python -c "import nviro_fetch"
# uv pip install /home/wspamer/dev/python/packages/nviro_fetch/dist/nviro_fetch-0.1.0-py3-none-any.whl
# uv pip install -e /home/wspamer/dev/python/packages/nviro_fetch/
```

## Private Repository

Reddit: <https://www.reddit.com/r/Python/comments/17tg1lk/third_party_private_package_hosting/>
Nexus: <https://help.sonatype.com/en/pypi-repositories.html>

## Install from Github

```bash
    pip install git+https://github.com/WSpamer/nviro_fetch.git#egg=nviro_fetch
    pip install git+https://github.com/<username>/<repository_name>.git#egg=<module_name>

```
