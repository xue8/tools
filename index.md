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
### Docker

```shell
#!/bin/bash

set -ue

POD_NAME=${POD_NAME:-"log"}
UTIL_IMAGE=${UTIL_IMAGE:-"nginx"}
HOST_PORT=${HOST_PORT:-22}

pod_ns=$(kubectl get po -A | grep ${POD_NAME} | head -1 | awk '{print $1}')
pod_name=$(kubectl get po -A | grep ${POD_NAME} | head -1 | awk '{print $2}')
host_ip=$(kubectl get po -A -owide | grep ${POD_NAME} | head -1 | awk '{print $8}')

cmd1="container_id=\$(docker ps | grep ${pod_name} | grep -v 'pause' | awk '{print \$1}')"
cmd2="util_image=\$(kubectl get deploy -oyaml -n tce ${UTIL_IMAGE} | grep 'image:' | grep -v '#'| sed 's/ //g' | sed 's/image://g')"
cmd3="echo \"enter ${pod_name} using \${util_image}\""
cmd4="docker run -it --pid=container:\${container_id} --net=container:\${container_id} \${util_image} /bin/bash"

echo "login ${host_ip}, pod_ns ${pod_ns} pod_name ${pod_name} port ${HOST_PORT}"
ssh root@${host_ip} -p ${HOST_PORT} -t "set -x; ${cmd1}; ${cmd2}; ${cmd3}; ${cmd4}"
```

## Alfred
- [alfred-workflows/awesome-alfred-workflows: A curated list of awesome alfred workflows](https://github.com/alfred-workflows/awesome-alfred-workflows)
- [jopemachine/alfred-chromium-workflow: Chromium based browser workflow for Alfred 5](https://github.com/jopemachine/alfred-chromium-workflow)
- [bchatard/alfred-jetbrains: Alfred4 workflow to easily open your projects with your favorite JetBrains product.](https://github.com/bchatard/alfred-jetbrains)
- [xue8/alfred-tools](https://github.com/xue8/alfred-tools)

