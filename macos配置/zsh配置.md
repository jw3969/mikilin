##### ~ 目录下

默认zsh环境（echo $0）
运行
    curl -sSL "https://github.com/zthxxx/jovial/raw/master/jovial.zsh-theme" -o ~/.config/jovial.zsh-theme
下载配置文件
使用
    source ~/.config/jovial.zsh-theme
更新配置

**.zshrc配置文件中，已经进行了区分，打开wezterm时启用starship美化，而打开terminal时启用zsh-jovial美化**
**conda 懒启动**
**如果安装的是miniconda，记得把anaconda3改成miniconda3**

**如果homebrew的python优先级落后于系统的python，可能是zprofile中没有设置路径，记得检查**


##### .zshrc
```
# alias python=python3
# caffeinate -d 防止黑屏 -i 防后台任务中断 -t 秒数 

# 自动建议
source $(brew --prefix)/share/zsh-autosuggestions/zsh-autosuggestions.zsh

# 问候
greet_user() {
    current_time=$(date +"%Y-%m-%d %H:%M:%S")
    echo "$USER 主人,为您报时: $current_time"
    echo "每日一问，您找到npy了吗?"
}
[[ -o interactive ]] && greet_user

source ~/.config/jovial.zsh-theme

# ===== conda（全局懒加载）=====
conda() {
    unset -f conda
    source /opt/anaconda3/etc/profile.d/conda.sh
    conda "$@"
}

# Homebrew 不自动更新
export HOMEBREW_NO_AUTO_UPDATE=true

export PATH="$HOME/.local/bin:$PATH"

# ===== 语法高亮（必须放最后）=====
source $(brew --prefix)/share/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh
```

##### .zprofile
```
# Homebrew 环境
export PATH="/opt/homebrew/bin:$PATH"
eval "$(/opt/homebrew/bin/brew shellenv)"
# eval "$(/opt/homebrew/bin/brew shellenv zsh)"
```
