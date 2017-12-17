# GitGames
Awesome git games that can be a fun way to learn git

1. https://learngitbranching.js.org/
2. https://www.git-game.com/

### Solutions to Git-Game-v1
| Level | Solution |
|:-----:|:--------:|
| 1 | git checkout 6402 |
| 2 | git checkout bug |
| 3 | git blame cool.cpp > git checkout LinusTorvalds2014 |
| 4 | vim .gitignore |
| 5 | git checkout tree |
| 6 | /outputclue.sh nextclue_input.cpp |
| 7 | git fetch origin/code4life <br>git merge origin/code4life <br>./outputclue.sh nextclue_input.cpp <br>git checkout mouse |
| 8 | git diff mouse bug -- remember <br>git checkout Henry |
| 9 | git checkout origin/Henry |
| 10 | git remote add remote https://github.com/drami025/git-game.git <br>git pull remote master |

### Solution to Git-Game-v2
| Level | Solution |
|:-----:|:--------:|
| 1 | git ls-files | xargs wc -l <br>git checkout 6861 |
| 2 | git log <br>git show 16a28 <br>git checkout snowden |
| 3 | git shortlog <br>git checkout anon |
| 4 | git describe <br>git checkout return <br>git checkout preety |
| 5 | git log --pretty=format:"%t  %s <br>git checkout SIGPOLL <br>git log --pretty=format: ''tree hash: %t --> subject: %s'' |
| 6 | git submodule init <br>git submodule update --init --recursive <br>cd Java <br>cd .. <br>git checkout history <br>git submodule init #then  git submodule update |
| 7 | git log -p --full-diff (can use git grep and git rev-list) <br>git checkout cherry <br>git grep "@hint" $(git rev-list history) |
| 8 | git checkout arachnid <br>git checkout HEAD\~4 <br>git checkout insect <br>git checkout HEAD\~3 <br>git checkout cherry <br>git cherry-pick 180fc7bb b441b5bb <br>cat consonents.txt && vowels.txt <br>git checkout lighthouse <br>git cherry-pick arachnid\~4 insect\~3 |
| 9 | git bisect start <br>git log --pretty=oneline --reverse | head -1 <br>git bisect good 394217 <br>git log --preety=oneline --reverse | tail -1 <br>git bisect bad 662efa <br>cat twinkle.txt <br>git bisect bad / git bisect good <br>ls <br>cat message <br>git checkout root |
