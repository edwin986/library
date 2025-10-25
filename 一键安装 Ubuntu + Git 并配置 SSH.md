## 一键安装 Ubuntu + Git 并配置 SSH

```
#!/data/data/com.termux/files/usr/bin/bash
# 一键安装 Ubuntu + Git 并配置 SSH

# === 配置区域（改成你自己的） ===
GIT_NAME="你的名字"
GIT_EMAIL="你的邮箱@example.com"
# ==============================

# 1. 更新 Termux
pkg update -y && pkg upgrade -y

# 2. 安装 proot-distro
pkg install proot-distro -y

# 3. 安装 Ubuntu 22.04
proot-distro install ubuntu

# 4. 在 Ubuntu 里执行配置
proot-distro login ubuntu -- bash << EOF
apt update -y && apt upgrade -y
apt install git openssh -y

git config --global user.name "$GIT_NAME"
git config --global user.email "$GIT_EMAIL"

# 如果没有 SSH key 就生成一个
if [ ! -f ~/.ssh/id_ed25519 ]; then
    ssh-keygen -t ed25519 -C "$GIT_EMAIL" -f ~/.ssh/id_ed25519 -N ""
fi

echo "===== 你的公钥如下，复制到 GitHub/Gitee SSH Keys 设置里 ====="
cat ~/.ssh/id_ed25519.pub
EOF

echo "✅ 完成！下次进入 Ubuntu 用: proot-distro login ubuntu"

这样保存为 setup-ubuntu-git.sh
然后在 Termux 里运行：
setup-ubuntu-git.sh
就能一键完成。
```