
# How I am using Obsidian

This topic will explain how I am using Obsidian and the structure used.

## 📚 Obsidian Repository Structure
<pre>
obsidian-notes → <a href="http://gitlab.lab.local/obsidian/obsidian-notes">GitLab</a>
├── csl → <a href="http://gitlab.lab.local/obsidian/csl.git">GitLab</a>
├── pessoal → <a href="http://gitlab.lab.local/obsidian/pessoal.git">GitLab</a>
└── study → <a href="http://gitlab.lab.local/obsidian/study">GitLab</a> | <a href="https://github.com/eduardocarneiro/study.git">Github</a>
    ├── cloud
    │   ├── aws
    │   │   ├── 01-services
    │   │   │   └── 01-iam
    │   │   └── 02-aws-exams
    │   │       └── 01-saa-c03
    │   │           └── 01-saa-c03-tutorialdojo → <a href="http://gitlab.lab.local/obsidian/01-saa-c03-tutorialdojo.git">GitLab</a>
    │   ├── azure
    │   │   ├── 01-services
    │   │   └── 02-azure-exams → <a href="http://gitlab.lab.local/obsidian/02-azure-exams.git">GitLab</a>
    │   ├── google
    │   │   ├── 01-services
    │   │   └── 02-google-exams → <a href="http://gitlab.lab.local/obsidian/02-google-exams">GitLab</a>
    │   └── projects
    │       ├── project-aws-01-aaa → <a href="http://gitlab.lab.local/obsidian">GitLab</a> | <a href="https://github.com/eduardocarneiro/study.git">Github</a>
    │       ├── project-aws-02-bbb → <a href="http://gitlab.lab.local/obsidian">GitLab</a> | <a href="https://github.com/eduardocarneiro/study.git">Github</a>
    │       ├── project-azure-01-aaa → <a href="http://gitlab.lab.local/obsidian">GitLab</a> | <a href="https://github.com/eduardocarneiro/study.git">Github</a>
    │       └── project-google-01-aaa → <a href="http://gitlab.lab.local/obsidian">GitLab</a> | <a href="https://github.com/eduardocarneiro/study.git">Github</a>
    ├── code
    ├── devops
    │   ├── 01-kubernetes
    │   │   ├── 01-k8s
    │   │   ├── 02-openshift
    │   │   ├── 03-eks
    │   │   ├── 04-aks
    │   │   ├── 05-gke
    │   │   └── 06-k3s
    │   ├── 02-ci-cd
    │   ├── 03-gitops
    │   ├── 04-iac
    │   ├── 05-git
    │   └── projects
    │       ├── project-devops-01-aaa → <a href="http://gitlab.lab.local/obsidian">GitLab</a> | <a href="https://github.com/eduardocarneiro/study.git">Github</a>
    │       └── project-devops-02-bbb → <a href="http://gitlab.lab.local/obsidian">GitLab</a> | <a href="https://github.com/eduardocarneiro/study.git">Github</a>
    ├── obsidian
    ├── os
    ├── readme
    └── web3
</pre>

> to get this structure above I used the command `tree -d -L 6 obsidian-notes`


## **How to work with Obsidian and repositories Git**

From my Linux home directory I do a `git clone` from my first repository `obsidian-notes`

```bash
eduardo@eoc:~$ git clone http://gitlab.lab.local/obsidian/obsidian-notes.git
eduardo@eoc:~$ cd obsidian-notes
eduardo@eoc:~/obsidian-notes$
```

### **obsidian-notes** 

Inside the `obsidian-notes` repository directory I do the clone for the others repositories like: `csl`, `pessoal`, `study` and etc.

This `obsidian-notes` repository is used only to hold all Obsidian configuration as we can see below:
```bash 
eduardo@eoc:~/obsidian-notes$ ls -la .obsidian/
total 56
drwxr-xr-x 4 eduardo users 4096 May  7 20:54 .
drwxr-xr-x 7 eduardo users 4096 May  7 20:56 ..
-rw-r--r-- 1 eduardo users   46 May  7 20:54 app.json
-rw-r--r-- 1 eduardo users   72 Apr 30 21:16 appearance.json
-rw-r--r-- 1 eduardo users   54 Apr 30 21:16 community-plugins.json
-rw-r--r-- 1 eduardo users  696 Apr 30 21:16 core-plugins.json
-rw-r--r-- 1 eduardo users   98 Apr 30 21:16 daily-notes.json
-rw-r--r-- 1 eduardo users  493 Apr 30 21:16 graph.json
-rw-r--r-- 1 eduardo users    2 Apr 30 21:16 hotkeys.json
drwxr-xr-x 6 eduardo users 4096 Apr 30 21:16 plugins
-rw-r--r-- 1 eduardo users   18 Apr 30 21:16 templates.json
drwxr-xr-x 3 eduardo users 4096 Apr 30 21:16 themes
-rw-r--r-- 1 eduardo users 6890 May  7 21:33 workspace.json

```

The other important file is the `.gitignore` , It is used to ignore the sub repository directories created later, like `csl`, `pessoal`, `study` and etc.
```bash 
eduardo@eoc:~/obsidian-notes$ cat .gitignore 
# --- Repositórios e Diretórios Independentes ---
# Bloqueia o rastreamento das pastas completas pelo repositório pai
pessoal/
study/
csl/
redhat/
notes/


# --- Obsidian Internals (Configurações locais e cache) ---
.obsidian/workspace.json
.obsidian/workspace-mobile.json
.obsidian/cache/
.obsidian/indexed-db/

# --- Arquivos de Sistema ---
.DS_Store
Thumbs.db
*.tmp

```

As we can see in `Obsidian Repository Structure` , this repository is a local repository in my local gitlab. In that case I have only one remote diretory like we can se below:
```bash
eduardo@eoc:~/obsidian-notes$ git remote -v
origin	http://gitlab.lab.local/obsidian/obsidian-notes.git (fetch)
origin	http://gitlab.lab.local/obsidian/obsidian-notes.git (push)
eduardo@eoc:~/obsidian-notes$ 

```

### **csl**

This repository is a private repository that is stored in my `Gitlab local`.

In that case we just need to clone the directory and make sure It is included in `.gitignore` from `obsidian-notes` repo.

```bash
eduardo@eoc:~/obsidian-notes$ git clone http://gitlab.lab.local/obsidian/csl.git
```

### **pessoal**

This repository is a private repository that is stored in my `Gitlab local`.

In that case we just need to clone the directory and make sure It is included in `.gitignore` from `obsidian-notes` repo.

```bash
eduardo@eoc:~/obsidian-notes$ git clone http://gitlab.lab.local/obsidian/pessoal.git
```

### **study**

The Study repository will be used to document all tests I do to learn things.

This repository is a private and public repository that is stored in my Gitlab Local and in my Github, as you can see below:

```bash 
eduardo@eoc:~/obsidian-notes/study$ git remote -v
github	https://github.com/eduardocarneiro/study.git (fetch)
github	https://github.com/eduardocarneiro/study.git (push)
origin	http://gitlab.lab.local/obsidian/study.git (fetch)
origin	http://gitlab.lab.local/obsidian/study.git (push)

```

**What I did to work with both repositories:**
1. create a `study` repository on Gitlab local
	It was created on `http://gitlab.lab.local/obsidian/study.git`

2. clone it inside `obsidian-notes` directory
```bash 
eduardo@eoc:~/obsidian-notes$ git clone http://gitlab.lab.local/obsidian/study.git
eduardo@eoc:~/obsidian-notes$ cd study/
```

> by the way, do the same procedure for all repositories you are using inside the `study`  repository. 

3.  create a `study` repository on Github
	It was created on `https://github.com/eduardocarneiro/study.git`

4. set a new remote git repository to `study` directory cloned before
```bash 
eduardo@eoc:~/obsidian-notes/study$ git remote set-url github https://github.com/eduardocarneiro/study.git
```

5.  create the `.gitignore`

	Do not forget to include all external repositories. For example the path `cloud/aws/02-aws-exams`  will be another repository inside gitlab and github.

```bash 
eduardo@eoc:~/obsidian-notes/study$ pwd
/home/eduardo/obsidian-notes/study

eduardo@eoc:~/obsidian-notes/study$ cat .gitignore 
# --- Repositórios e Diretórios Independentes ---
# Bloqueia o rastreamento das pastas completas pelo repositório pai
# Ignorar todas as subpastas dentro de 01-saa-c03, mas manter arquivos da raiz dela
cloud/aws/02-aws-exams/01-saa-c03/*/
#cloud/aws/02-aws-exams
#cloud/azure/02-azure-exams
#cloud/google/02-google-exams
cloud/projects/project-aws-01-aaa
cloud/projects/project-aws-02-bbb
cloud/projects/project-azure-01-aaa
cloud/projects/project-google-01-aaa
devops/projects/project-devops-01-aaa
devops/projects/project-devops-02-aaa

# --- Arquivos de Sistema ---
.DS_Store
Thumbs.db
*.tmp


# --- Arquivos de Sistema ---
.DS_Store
Thumbs.db
*.tmp
eduardo@eoc:~/obsidian-notes/study$ 
```

6. set up the global credential 

	Type the command below once and it will store the your credential inside the file `~/.git-credentials` , after you first push

```bash 
eduardo@eoc:~/obsidian-notes/study$ git config --global credential.helper store

eduardo@eoc:~/obsidian-notes/study$ git remote -v
github	https://github.com/eduardocarneiro/study.git (fetch)
github	https://github.com/eduardocarneiro/study.git (push)
origin	http://gitlab.lab.local/obsidian/study.git (fetch)
origin	http://gitlab.lab.local/obsidian/study.git (push)

eduardo@eoc:~/obsidian-notes/study$ git push origin 

eduardo@eoc:~/obsidian-notes/study$ git push github

```

**To make the life easier I created the script below:**
```bash 
eduardo@eoc:~/obsidian-notes/study$ cat /home/eduardo/my-scripts/commit_v4.sh
#!/bin/bash

# =========================
# 🔧 CONFIG
# =========================
DEFAULT_REMOTE="origin"

# =========================
# 📥 ADD
# =========================
git add .

files=$(git diff --cached --name-only)

if [ -z "$files" ]; then
  echo "Nada para commit"
  exit 0
fi

# =========================
# 📁 SCOPE INTELIGENTE
# =========================
scope=""

if echo "$files" | grep -qi "aws"; then
  if echo "$files" | grep -qi "iam"; then
    scope="aws-iam"
  else
    scope="aws"
  fi
elif echo "$files" | grep -qi "kubernetes\|k8s"; then
  scope="k8s"
elif echo "$files" | grep -qi "terraform"; then
  scope="terraform"
else
  scope=$(echo "$files" | awk -F/ '{print $1}' | sort | uniq | tr '\n' '-' | sed 's/-$//')
fi

# =========================
# 🔍 TYPE DETECTION
# =========================
type="chore"

diff_content=$(git diff --cached)

if echo "$files" | grep -qi "\.md"; then
  type="docs"
elif echo "$diff_content" | grep -qi "fix\|bug\|error"; then
  type="fix"
elif echo "$diff_content" | grep -qi "refactor\|rename"; then
  type="refactor"
elif echo "$files" | grep -qi "\.sh\|\.yaml\|\.yml"; then
  type="chore"
else
  type="feat"
fi

# =========================
# 📊 DIFF STATS
# =========================
added=$(git diff --cached --numstat | awk '{add+=$1} END {print add}')
removed=$(git diff --cached --numstat | awk '{del+=$2} END {print del}')

# =========================
# 🧠 SMART DESCRIPTION
# =========================
main_file=$(echo "$files" | head -n 1)
filename=$(basename "$main_file")

# tenta extrair contexto mais humano
if echo "$main_file" | grep -qi "iam"; then
  context="IAM"
elif echo "$main_file" | grep -qi "ec2"; then
  context="EC2"
elif echo "$main_file" | grep -qi "s3"; then
  context="S3"
else
  context="$filename"
fi

# descrição base
if [ "$type" == "docs" ]; then
  description="update $context documentation"
elif [ "$type" == "fix" ]; then
  description="fix issue in $context"
elif [ "$type" == "refactor" ]; then
  description="refactor $context"
elif [ "$type" == "feat" ]; then
  description="add/update $context"
else
  description="update $context"
fi

# =========================
# ✨ FINAL MESSAGE
# =========================
commit_msg="$type($scope): $description (+$added/-$removed)"

# =========================
# 🖥️ PREVIEW
# =========================
echo ""
echo "📂 Arquivos:"
echo "$files"
echo ""

echo "📊 Stats:"
echo "  +$added / -$removed"
echo ""

echo "💡 Sugestão:"
echo "  $commit_msg"
echo ""

# editar
read -p "✏️  Editar mensagem (Enter = aceitar): " user_msg

if [ -n "$user_msg" ]; then
  commit_msg="$user_msg"
fi

echo ""
echo "🚀 Commit:"
echo "  $commit_msg"
echo ""

read -p "Confirmar commit? (y/n): " confirm
if [ "$confirm" != "y" ]; then
  echo "Cancelado."
  exit 0
fi

# =========================
# 💾 COMMIT
# =========================
git commit -m "$commit_msg"

# =========================
# 🌐 ESCOLHA DO REMOTE
# =========================
echo ""
echo "🌐 Para onde enviar?"
echo "1) origin (GitLab)"
echo "2) github"
echo "3) ambos"
echo ""

read -p "Escolha (1/2/3): " remote_choice

case $remote_choice in
  1)
    git push origin
    ;;
  2)
    git push github
    ;;
  3)
    git push origin
    git push github
    ;;
  *)
    echo "Opção inválida. Usando padrão: $DEFAULT_REMOTE"
    git push $DEFAULT_REMOTE
    ;;
esac

echo ""
echo "✅ Done."

```

**How to use it**

Create the script in some place in your machine. In my case I am holding my scripts inside the directory `/home/eduardo/my-scripts/` . The name of the script is `commit_v4.sh` , and I added it as a alias on `~/.bashrc` , like you can see below:
```bash 
eduardo@eoc:~/obsidian-notes/study$ grep -A 2 "gitlab" /home/eduardo/.bashrc
# Commit gitlab and github
#alias commit='/home/eduardo/my-scripts/commit.sh'
alias commit='/home/eduardo/my-scripts/commit_v4.sh'

```

After create the alias do not forget to run `source ~/.bashrc`.

To do your commit, you just need to run the command `commit`  inside the repository you did an update.

Below you can see `git status` , just to check the changes, then command `commit` .  

It will suggest you a commit message, and will ask you if you what to edit the message, just type `Enter` if It suggested message is OK. 
![[Pasted image 20260508231638.png]]

It will also ask you if you confirm the commit and if you want to commit in gitlab, github or both. As we added the credentials locally before, we do not need to type user and password all the time. 

```bash 
eduardo@eoc:~/obsidian-notes/study$ git status
On branch main
Your branch is up to date with 'origin/main'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   obsidian/README.md

no changes added to commit (use "git add" and/or "git commit -a")
eduardo@eoc:~/obsidian-notes/study$ commit

📂 Arquivos:
obsidian/README.md

📊 Stats:
  +240 / -0

💡 Sugestão:
  docs(obsidian): update README.md documentation (+240/-0)

✏️  Editar mensagem (Enter = aceitar): 

🚀 Commit:
  docs(obsidian): update README.md documentation (+240/-0)

Confirmar commit? (y/n): y
[main fe1e77c] docs(obsidian): update README.md documentation (+240/-0)
 1 file changed, 240 insertions(+)

🌐 Para onde enviar?
1) origin (GitLab)
2) github
3) ambos

Escolha (1/2/3): 3
Enumerating objects: 7, done.
Counting objects: 100% (7/7), done.
Delta compression using up to 12 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (4/4), 3.50 KiB | 3.50 MiB/s, done.
Total 4 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
To http://gitlab.lab.local/obsidian/study.git
   67597ff..fe1e77c  main -> main
Enumerating objects: 21, done.
Counting objects: 100% (21/21), done.
Delta compression using up to 12 threads
Compressing objects: 100% (8/8), done.
Writing objects: 100% (12/12), 4.15 KiB | 4.15 MiB/s, done.
Total 12 (delta 2), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (2/2), completed with 1 local object.
To https://github.com/eduardocarneiro/study.git
   aac88e6..fe1e77c  main -> main

✅ Done.

```

