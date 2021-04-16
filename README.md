# GIT comenzi + explicatii 

>Cheia succesului in GIT -> tragi ramura principala in repository-ul local || seara commit --> dimineata fetch -> pull ||

## <ins>basics</ins>
```bash
git init -> initializeaza un nou repository local
git add <nume_fisier> <nume_fisier> -> adaug fisierele specificate pentru a fi monitorizate de git
git add .     -> adaug toate fisierele
git commit -m 'titlu' -m 'descriere' -> salvez stadiul proiectului/fisierelor din etapa de stage
git commit -am 'titlu' -m 'descriere' -> ca mai sus dar sar peste etapa de add
            ^--fisierele neurmarite nu le adauga(doar pe cele din etapa de add)

git show        -> afiseaza ultimul commit de pe ramura pe care te aflii
git log         -> afiseaza commit-urile de pe ramura actuala
git log --all   -> afiseaza toate commit-urile, cu toate ramurile
git log --all --graph --decorate --oneline -> afiseaza grafic - cu sau fara optiuni -test

git merge <nume_ramura> -> trebuie sa ma aflu pe ramura in care vreau sa aduc schimbarile
git merge --abort -> anuleaza unirea ramurilor - in cazul conflictelor

git diff <commit_hash/node> <filename> -> pt a vedea modificarile fisierului

git checkout <numele_ramurei/hash> -> schimba ramura/punctul in care te aflii in cronologia repository-ului

    -f -> pt a forta ceva ex: git checkout -f show~1 ->nu ma lasa pt ca nu salvasem un fisier in repository
    ~1 ... ~x -> reprezinta cu cate commit-uri vrei sa mergi inapoi: git checkout main~2

git branch <nume_ramura_noua> -> creeaza o noua ramura
git checkout -b <nume_ramura> -> creeaza si trece pe acea noua ramura
git branch -> pt a vedea ramurile repository-ului local 
git branch -r -> pt a vedea ramurile repository-ului de pe server
git branch -m <new_name> -> modifica numele ramurii actuale
git branch --all -> pt a vedea toate ramurile existente local/remote

$ git branch -d <nume_ramura> -> sterge ramura locala (daca nu te aflii pe ea, altfel nu functioneaza), doar daca a fost unita cu cea principala
$ git branch -D <nume_ramura> -> sterge ramura locala fortat, indiferent daca a fost sau nu unita cu cea din care a deviat
$ git push -d <nume_remote> <branch_name> -> sterge ramura de pe server

git remote -v -> afiseaza remote-urile setate
git remote add <nume_remote> <link_adresa_github> -> denumeste si adauga serverul/repository remote 
git remote rename <old_name> <new_name> -> redenumeste remote-ul specificat
git remote -v remove <nume_remote> -> sterge serverul adaugat
            -v -> verbose ...practic iti afiseaza detalii

git push <nume_remote> <nume_ramura> -> pt a impinge pe server din rep.local pe o anume ramura 

                
git pull <nume_remote> -> trage intregul proiect(toate ramurile) de pe serverul remote
            ^--> cu sau fara(cred ca depinde spefcificarea numelui de setarile upstream )
git pull <nume_remote> <nume_ramura> -> trage de pe server in repo.local ramura specificata
        ^--> adauga -u pentru a seta modul implicit (nu mai scrii de fiecare data)
    
git reset <nod_commit/hash> -> muta HEAD-ul la acel nod/hash, sterge doar istoricul celor mai noi comitt-uri de pana la acel nod, dar fara a pierde modificarileefectuate proiectului
git reset --hard <nod_commit/hash> --> muta HEAD-ul la acel nod/has, sterge atat commit-urile, cat si datele
 `difera atunci cand HEAD-ul nu este la ultimul commit de pe acea ramura(practic are rol de checkout -cu sau fara modificarea datelor proiectului)`
```
## <ins>from somewhere else</ins>
```bash
git config --global user.name "name"
git config --global user.email "email"
     (--local option as well)
git init - initialize a new repo in a directory
git status - see the state of files in working tree, staging area vs latest commit in git history
git add - move file(s) to the staging area
git log - view the git history / git commit graph
git diff - diff of working tree and staging area
git diff --cached - diff of staging area and latest commit
git rm - remove a file from the working tree and the staging area
git checkout -- filename - retrieve a file from the staging area into the working tree
git reset HEAD filename - retrieve a file from the latest commit into the staging area
git checkout (commit hash) filename - retrieve a file from a previous commit
git log =  git history
git log --all --decorate --oneline --graph = commit history graph
git branch (branch-name) = create a branch
git checkout (branch-name) = checkout a branch/move head pointer
git commit -a -m "commit message" = commit all modified and tracked files in on command (bypass separate 'git add' command)
git diff master..SDN = diff between 2 branches
git merge (branch-name) = merge branches (fast-forward and 3-way merges)
git branch --merged = see branches merged into the current branch
git branch -d (branch-name) = delete a branch, only if already merged
git branch -D (branch-name) = delete a branch, including if not already merged (exercise caution here)
git merge --abort = abort a merge during a merge conflict situation
git checkout (commit-hash) = checkout a commit directly, not through a branch, results in a detached HEAD state
git stash = create a stash point
git stash list = list stash points
git stash list -p = list stash points and show diffs per stash
git stash apply = apply most recent stash
git stash pop = apply most recent stash, and remove it from saved stashes
git stash apply (stash reference) = apply a specific stash point
git stash save "(description)" = create a stash point, be more descriptive

Retrieve/Clone a repo = git clone (URL)
List remotes = git remote (-v for detail)
Commit graph = git log --all --decorate --oneline --graph
Checkout a branch = git checkout
Create and checkout a branch = git checkout -b (branch name)
Retrieve/download from a remote = git fetch (remote name)
merge branch or tracking-branch = git merge (branch or tracking branch name)
Show status = git status
Upload to a remote = git push (remote name) (branch name)
stage an edit = git add (filename)
make a commit = git commit -m "description"
stage and commit = git commit -a -m "description"
List local branches = git branch
List remote branches = git branch -r
List both local and remote branches = git branch -a

```
