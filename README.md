`[OO에 추가] 문구가 없는 경우는 terminal에 바로 붙여넣으면 됩니다`

## 키보드 한/영 전환(Karabinar_elements)
[Karabiner Elements 다운로드](https://karabiner-elements.pqrs.org/)
- Karabinar
  - Mac내장키보드: [right-command] > [f18]
  - 외장키보드: [right-option] > [f18]
- 키보드 > 단축키 >  입력소스 > 다음 입력 소스 선택(밑에거. 위에는 뗄때 입력됨) >( right-command를 누르면 F18로 설정이 됨)
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
- `~/Library/KeyBindings` 폴더에 `DefaultKeyBinding.dict` 파일을 만듭니다.
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
# brew 설치
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# Git output이 새로운 페이지에서 보이는 것을 막아줌
git config --global pager.branch false
```
**zsh 설치**
```
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

# zsh-syntax-highlighting
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting

# zsh-autosuggestions
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```

 
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

code () { VSCODE_CWD="$PWD" open -n -b "com.microsoft.VSCode" --args $* ;}
```

**`~/.zsh_aliases`**
```
alias desktop="cd ~/Desktop"
alias download="cd ~/Downloads"
alias clear='clear && printf "\e[3J"'

alias vpn="~/Desktop/vpn/vpn"

alias bookingweb="cd ~/Desktop/booking-web && nvm use 10"
alias bizowner="cd ~/Desktop/business-owner && nvm use"
alias mint="cd ~/Desktop/mint && nvm use 10"

alias gs="git status"
alias gb="git branch"
alias gpsu="git rev-parse --abbrev-ref HEAD | xargs -I {} git push --set-upstream origin {}"
alias gsu="git rev-parse --abbrev-ref HEAD | xargs -I {} git branch --set-upstream-to=origin/{} {}"
alias gbda="git branch | grep 'js/\|junsoo' | xargs -I {} git branch -D {}"
alias grh="git reset --hard"
alias grs="git reset --soft HEAD^"
alias gbd="git branch -D"
alias grestore="git restore --staged '*'"
alias udt-develop="git fetch origin develop:develop"
alias udt-main="git fetch origin main:main"

function gpfo() {
    git pull origin $1;
}
function seeport() {
    lsof -i tcp:$1;
}
```

**`~/.gitconfig`**
```
[pager]
    branch = false
[alias]
    co = checkout
    cp = cherry-pick
    lp = log --oneline --decorate
    lpg = log --oneline --decorate --graph
    rba = rebase --abort
    rbc = rebase --continue
    cm = commit -m
    aa = add --all
    bc = remote prune origin
```

[Ultimate Vim 설치](https://github.com/amix/vimrc)
```bash
echo "
set nu
set mouse=a
" | sudo tee -a ~/.vim_runtime/my_configs.vim
```

## iTerm2 꾸미기
- [chalkboard 테마 다운로드](https://drive.google.com/file/d/1iWwHFzSWTnuLMKlLg_bk2J7BW1z7uVCR/view?usp=sharing)
- 테마적용하기: Preferences > Profiles > Colors > Color Presets > Import
- 한글깨짐해결: Preferences > Profiles > Text > Unicode normalization form: `NFC`

## 필수 프로그램 
[Visual Studio Code 다운로드](https://code.visualstudio.com/download)
- Prettier 설치
- Eslint 설치
- Git lens 설치
- Command Palette > Open Keyboard Shortcuts > Replace (`cmd + h`)
- Command Palette > install 'code' command in PATH
  - 안될시 `~/.zshrc`에 `code () { VSCODE_CWD="$PWD" open -n -b "com.microsoft.VSCode" --args $* ;}`

[Notion 다운로드](https://www.notion.so/desktop/mac/download)

[Zoom 다운르도](https://zoom.us/download#client_4meeting)

[마우스와 트랙패드 반대로](https://mos.caldis.me/)

## Project Setup
**NVM 설치** [링크](https://github.com/nvm-sh/nvm)
```
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.38.0/install.sh | bash

source ~/.zshrc
nvm install 16
```

**yarn 설치**
```
npm install --global yarn
```

## Extra
- `brew install fd`
- `Safari Technology Preview`
