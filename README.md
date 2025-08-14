## Hi there 👋

#### *沉舟侧畔千帆过 · 病树前头万木春*

梓橙 林梓橙 梓橙 · 西奈 橙奈

###### TODO: 雨橙 林雨橙 Rain-mikan

<p align="center">
  <img src="background.jpg" alt="background">
</p>

##### 为你之后的 commit 签名

```
#!/bin/sh
set -e

USER_NAME="your-github-username"
USER_EMAIL="your-github-email@example.com"

SSH_KEY_PATH="$HOME/.ssh/id_ed25519.pub"
PRIV_KEY="${SSH_KEY_PATH%.pub}"

if [ ! -f "$SSH_KEY_PATH" ]; then
  mkdir -p "$(dirname "$SSH_KEY_PATH")"
  ssh-keygen -t ed25519 -C "$USER_EMAIL" -f "$PRIV_KEY" -N "" >/dev/null
fi

git config --global user.name "$USER_NAME"
git config --global user.email "$USER_EMAIL"
git config --global gpg.format ssh
git config --global user.signingkey "$SSH_KEY_PATH"
git config --global commit.gpgsign true

echo "Your SSH public key: $(cat "$SSH_KEY_PATH")"
echo "Add this SSH public key to your GitHub account as a signing key to display the “Verified” badge on your commits."
```