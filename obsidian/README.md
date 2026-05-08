
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
    │   │   └── 02-aws-exams → <a href="http://gitlab.lab.local/obsidian/02-aws-exams.git">GitLab</a>
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

> to get this structure above I used the command `tree -d -L 5 obsidian-notes`


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

