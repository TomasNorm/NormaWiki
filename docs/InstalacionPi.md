# Easpberry pi para test

##### instalacion de GitHUB  
```console
type -p curl >/dev/null || (sudo apt update && sudo apt install curl -y)
curl -fsSL https://cli.github.com/packages/githubcli-archive-keyring.gpg | sudo dd of=/usr/share/keyrings/githubcli-archive-keyring.gpg 
&& sudo chmod go+r /usr/share/keyrings/githubcli-archive-keyring.gpg 
&& echo “deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main” | sudo tee /etc/apt/sources.list.d/github-cli.list > /dev/null 
&& sudo apt update 
&& sudo apt install gh -y
```
  

TOKEN = ‘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’


##### instalacion de requisitos

```console
pip3 install -r requirements.txt
```
