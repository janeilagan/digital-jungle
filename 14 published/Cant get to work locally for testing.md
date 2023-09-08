---
alias: testing netlify and obsidian-zola locally
tags:
- published
- index/00.01
- index/23.02
---


Follow: [How to test serverless functions locally (netlify.com)](https://www.netlify.com/blog/2021/12/12/how-to-test-serverless-functions-locally/)
- Download https://www.getzola.org/documentation/getting-started/installation/ and depackage installer
- Run the ff:

```bash
sudo apt install python-is-python3 python3-pip
pip3 install python-slugify rtoml
sudo apt-get install rsync
```

- Clone obsidian-zola repo
- Set environment variable
- To convert windows path to wsl use:

```bash
wslpath -a "PATH"
```


```bash
sudo nano ~/.bashrc
export VAULT="PATH"
```

- ^X to exit, then save.


# 2023-05-17

- This now works using this: https://github.com/ppeetteerrs/obsidian-zola#local-testing-ubuntu-thanks-trwbox
- then:
```bash
cd obsidian-zola
./local-run.sh
```

# 2023-06-27

If you get `-bash: ./local-run.sh: /bin/bash^M: bad interpreter: No such file or directory` try this:

Install dos2unix then run command as sudo:

```bash
sudo apt-get install dos2unix
```

```bash
dos2unix local-run.sh
```

# 2023-08-24

