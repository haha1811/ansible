# ansible

## 2025-10












---

## create a new repository on the command line

```bash
echo "# ansible" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin git@github.com:haha1811/ansible.git
git push -u origin main
```

## push an existing repository from the command line

```bash
git remote add origin git@github.com:haha1811/ansible.git
git branch -M main
git push -u origin main
```

---

:::info
好 👍 我幫你整理一份 **Cloud9 新增專案並推送到 GitHub 新 repo 的 SOP**，簡單 5 個步驟，之後你照這樣操作就不會再卡到 SSH Key 或 remote 問題。
:::

---

## 🚀 Cloud9 → GitHub Public Repo SOP

### ✅ 前置條件（只要做一次就好）

* 你的 **帳號層級 SSH Key** 已經加到 GitHub（剛才完成了）。
* `~/.ssh/config` 已設定強制用這把金鑰連 GitHub，例如：

  ```sshconfig
  Host github.com
    HostName github.com
    User git
    IdentityFile ~/.ssh/id_ed25519   # 這是你帳號金鑰的路徑
    IdentitiesOnly yes
  ```

檢查一下：

```bash
ssh -T git@github.com
# 期望看到：Hi haha1811! You've successfully authenticated...
```

---

### 📝 每次新建專案流程

#### 1. 在 GitHub 建新 repo

例如建立 **abc**（public/private 都可以）。

不要勾「Initialize with README」，保持空的 repo（避免 push 衝突）。

---

#### 2. 在 Cloud9 建資料夾 & 初始化 git

```bash
cd ~/environment
mkdir abc && cd abc

git init
```

---

#### 3. 建一個 README 或程式碼檔案

```bash
echo "# abc project" >> README.md
git add README.md
git commit -m "first commit"
```

---

#### 4. 加上 remote

```bash
git remote add origin git@github.com:haha1811/abc.git
```

檢查一下：

```bash
git remote -v
# 會顯示 git@github.com:haha1811/abc.git
```

---

#### 5. 推送到 GitHub

```bash
git branch -M main
git push -u origin main
```

成功後，之後只要：

```bash
git add .
git commit -m "update"
git push
```

就能同步更新到 GitHub。

---

### 🔑 小抄

* **第一次推新專案** → `git push -u origin main`
* **之後每次更新** → `git push`
* **確認 remote** → `git remote -v`
* **確認 SSH 有效** → `ssh -T git@github.com`

---


