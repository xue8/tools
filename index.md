## Welcome to Tools Pages


### tmux

[.tmux/.tmux.conf at master · gpakosz/.tmux](https://github.com/gpakosz/.tmux/blob/master/.tmux.conf)

```shell
setw -g mode-keys vi # 开启vi风格后，支持vi的C-d、C-u、hjkl等快捷键
tmux_conf_copy_to_os_clipboard # 开启 C-v、C-b复制
```

### kubectl

```shell
alias k="kubectl"
alias pa='kubectl get pod --all-namespaces -o wide'
alias pag='kubectl get pod --all-namespaces -o wide |grep '
alias pagw='kubectl get pod --all-namespaces -o wide -w |grep'
alias paw='kubectl get pod --all-namespaces -o wide -w '
alias pd='kubectl -n tce describe pod'
alias sa='kubectl get svc --all-namespaces -o wide'
alias sag='kubectl get svc --all-namespaces -o wide |grep '
alias sagw='kubectl get svc --all-namespaces -o wide -w |grep'
alias saw='kubectl get svc --all-namespaces -o wide -w '
alias kg='kubectl get pod --all-namespaces -o wide |grep '
alias kgs='kubectl get svc --all-namespaces -o wide |grep '
```
