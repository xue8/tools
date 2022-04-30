## Welcome to Tools Pages


### tmux

[.tmux/.tmux.conf at master · gpakosz/.tmux](https://github.com/gpakosz/.tmux/blob/master/.tmux.conf)

```shell
setw -g mode-keys vi # 开启vi风格后，支持vi的C-d、C-u、hjkl等快捷键
```

### kubectl

```shell
alias k="kubectl"
alias kg="kubectl get po -A -owide | grep "
alias ka="kubectl get po -A -owide"
alias kgs="kubectl get -A -owide svc | grep "
```
