- 不要随便`upgrade`，小心软件突然用不了！重要升级版本前请备份系统！
- 有时，想升级到最新版本，提示依赖不满足，那就：
  - 例如，可以`apt-cache madison docker-ce`
  - 出来的字符串（比如`5:18.09.0~3-0~ubuntu-bionic`这种东西）拿去从高版本到低版本，一个一个试（比如`apt install docker-ce=5:18.09.0~3-0~ubuntu-bionic`），看什么时候能装即可
    - 当然，不一定要一个一个试。二分也行（太高则不满足其底层的依赖，太低则表层软件的依赖不满足。可能只有中间某个版本可以）