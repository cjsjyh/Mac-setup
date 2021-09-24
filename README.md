## 키보드 한/영 전환(arabinar_elements)

- Karabinar: From key: [right-option] To key: [f18]
- 키보드 > 단축키 >  입력소스 > 이전 입력 소스 선택 >( right-command를 누르면 F18로 설정이 됨)
- 키보드 > 입력소스 > 한/영키로 ABC 입력소스 전환 해제

## 원화로 나오는 것을 (`)로 바꾸기
```bash
mkdir ~/Library/KeyBindings
echo "{
 "₩" = ("insertText:", "`");
}" | sudo tee -a ~/Library/KeyBindings/DefaultkeyBinding.dict
```
<details>
<summary> 수동 </summary>

- `~/Library` 폴더에 `KeyBindings` 폴더를 추가합니다.
- `~/Library/KeyBindings` 폴더에 `DefaultkeyBinding.dict` 파일을 만듭니다.
- `DefaultkeyBinding.dict` 파일에 아래의 코드를 추가합니다.
```
{
    "₩" = ("insertText:", "`");
}
```
- 저장하고 맥을 재부팅(바로 적용되는 경우도 있지만 재부팅을 해야만 적용되는 경우가 많으니 재부팅을 추천드립니다.)
</details>

## 터미널 세팅
[iterm2 다운로드](https://iterm2.com/downloads/stable/latest)
```
// brew 설치
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

// Git output이 새로운 페이지에서 보이는 것을 막아줌
git config --global pager.branch false
```
**zsh 설치**
```
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

// zsh-syntax-highlighting
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting

// zsh-autosuggestions
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```
**`~/.zshrc`에 추가**
```
plugins=(
  git
  zsh-syntax-highlighting # 추가됨
  zsh-autosuggestions # 추가됨
)
```

```bash
echo "
source ~/.zsh_aliases
PROMPT='${ret_status} %{$fg[cyan]%}%~%{$reset_color%} $(git_prompt_info) '
" | sudo tee -a ~/.zshrc

echo "
alias desktop="cd ~/Desktop"
alias download="cd ~/Downloads"

alias gs="git status"
alias gpsu="git rev-parse --abbrev-ref HEAD | xargs -I {} git push --set-upstream origin {}"
alias gsu="git rev-parse --abbrev-ref HEAD | xargs -I {} git branch --set-upstream-to=origin/{} {}"
function gbda() {
    git branch | grep 'junsoo/' | xargs git branch -D
}
function gpfo() {
    git pull origin $1;
}
function seeport() {
    lsof -i tcp:$1;
}
" | sudo tee -a ~/.zsh_aliases

echo "
[alias]
    co = checkout
    cp = cherry-pick
    lp = log --oneline --decorate
    lpg = log --oneline --decorate --graph
    rba = rebase --abort
    rbc = rebase --continue
    cm = commit -m
    aa = add --all
" | sudo tee -a ~/.gitconfig
```

<details>
<summary>수동</summary>
 
**`~/.zshrc`**
```
plugins=(
  git
  zsh-syntax-highlighting
  zsh-autosuggestions
)

// 마지막에
source ~/.zsh_aliases
PROMPT='${ret_status} %{$fg[cyan]%}%~%{$reset_color%} $(git_prompt_info) '
```

**`~/.zsh_aliases`**
```
alias desktop="cd ~/Desktop"
alias download="cd ~/Downloads"

alias gs="git status"
alias gpsu="git rev-parse --abbrev-ref HEAD | xargs -I {} git push --set-upstream origin {}"
alias gsu="git rev-parse --abbrev-ref HEAD | xargs -I {} git branch --set-upstream-to=origin/{} {}"
function gbda() {
    git branch | grep 'junsoo/' | xargs git branch -D
}
function gpfo() {
    git pull origin $1;
}
function seeport() {
    lsof -i tcp:$1;
}
```

**`~/.gitconfig`**
```
[alias]
    co = checkout
    cp = cherry-pick
    lp = log --oneline --decorate
    lpg = log --oneline --decorate --graph
    rba = rebase --abort
    rbc = rebase --continue
    cm = commit -m
    aa = add --all
```
</details>
[Vim 세팅](https://github.com/amix/vimrc)
```
// ~/.vim_runtime/my_configs.vim
set nu
set mouse=a
```

## iTerm2 꾸미기
- [chalkboard 테마 다운로드](https://drive.google.com/file/d/1iWwHFzSWTnuLMKlLg_bk2J7BW1z7uVCR/view?usp=sharing)
- 테마적용하기: Preferences > Profiles > Colors > Color Presets > Import
- 한글깨짐해결: Preferences > Profiles > Text > Unicode normalization form: `NFC`

## 필수 프로그램 
[Visual Studio Code 다운로드](https://code.visualstudio.com/sha/download?build=stable&os=darwin-universal)
- Prettier 설치
- Eslint 설치

[Notion 다운로드](https://www.notion.so/desktop/mac/download)

[Zoom 다운르도](https://zoom.us/download#client_4meeting)


## Project Setup
`NVM`

## Extra
`brew install fd`
