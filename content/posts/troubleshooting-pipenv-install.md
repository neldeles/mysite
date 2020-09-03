+++
categories = []
date = 2020-09-02T16:00:00Z
draft = true
tags = []
title = "Troubleshooting Pipenv Install"

+++
User installation of pipenv.

<!--more-->

I was able to successfully install pip env via `pip3 install --user pipenv.`

However, when I run the command pipenv install in a fresh root project directory I receive the following message: `-bash: pipenv: command not found.`

To fix, need to follow the official instructions found [here](https://pipenv.pypa.io/en/latest/install/#installing-pipenv).

The exact commands I used were: 

\`\`\`

    PYTHON_BIN_PATH="$(python3 -m site --user-base)/bin"
    PATH="$PATH:$PYTHON_BIN_PATH"

\`\`\`

Source: [https://stackoverflow.com/questions/46391721/pipenv-command-not-found](https://stackoverflow.com/questions/46391721/pipenv-command-not-found "https://stackoverflow.com/questions/46391721/pipenv-command-not-found")