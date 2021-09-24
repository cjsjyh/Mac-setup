[iterm2 다운로드](https://iterm2.com/downloads/stable/latest)
zsh 설치: sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

brew 설치:
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

[Visual Studio Code 다운로드](https://code.visualstudio.com/sha/download?build=stable&os=darwin-universal)

[Notion 다운로드](https://www.notion.so/desktop/mac/download)

[iterm2 다운로드](https://iterm2.com/downloads/stable/latest)
zsh 설치: sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

brew install fd
---------------------------
원화로 나오는 것을 (`)로 바꾸기
~/Library 폴더에 KeyBindings 폴더를 추가합니다.
~/Library/KeyBindings 폴더에 DefaultkeyBinding.dict 파일을 만듭니다.
DefaultkeyBinding.dict 파일에 아래의 코드를 추가합니다.
{
    "₩" = ("insertText:", "`");
}

저장하고 맥을 재부팅합니다.
바로 적용되는 경우도 있지만 재부팅을 해야만 적용되는 경우가 많으니 재부팅을 추천드립니다.
----------------------------
git config --global pager.branch false
Git output이 새로운 페이지에서 보이는 것을 막아줌
----------------------------
# zsh-syntax-highlighting
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting

# zsh-autosuggestions
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions

~/.zshrc에 추가하기
plugins=(
  git
  zsh-syntax-highlighting
  zsh-autosuggestions
)

.zshrc 마지막에 
PROMPT='${ret_status} %{$fg[cyan]%}%~%{$reset_color%} $(git_prompt_info)'
----------------------------
karabinar_elements
Karabinarr: From key: [right-option] To key: [f18]
키보드 > 단축키 >  입력소스 > 이전 입력 소스 선택 >( right-command를 누르면 F18로 설정이 됨)
키보드 > 입력소스 > 한/영키로 ABC 입력소스 전환 해제

--------------------
~/.gitconfig
[alias]
    co = checkout
    cp = cherry-pick
    lp = log --pretty=oneline
    ra = rebase --abort
    rc = rebase --continue
    cm = commit -m
    aa = add --all

