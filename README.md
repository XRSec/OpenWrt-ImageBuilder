# OpenWrt imagebuilder with [@kiddin9](https://github.com/kiddin9/)

[1]: https://github.com/XRSec/OpenWrt-ImageBuilder/actions/workflows/build-openwrt.yml/badge.svg
[2]: https://github.com/XRSec/OpenWrt-ImageBuilder/actions/workflows/build-openwrt.yml
[3]: https://img.shields.io/badge/By-kiddin9-brightgreen.svg
[4]: https://github.com/kiddin9/OpenWrt_x86-r2s-r4s

[![编译 OpenWrt][1]][2]
[![kiddin9][3]][4]

> 来自一位菜鸡的辛勤耕耘

## 使用方式

1. 云编译 `Forks->Settings->Secrets->TOKEN_GITHUB`
2. 自定义设备 `devices/x86_64/settings.ini`
  ```bash
  jobs:
  Build:
    runs-on: ubuntu-20.04
    strategy:
      matrix:
        target: [x86_64,n1,arm64]
  # 注意, 部分固件的参数与本仓库使用的固件不符合,但是不影响使用
  # 如果有好的建议,欢迎提交 issue 和 我们一起完善 系统
  ```
3. 完全自定义 `devices/x86_64/settings.ini` `files/root/.zshrc`

4. 如果不填写参数,将会以配置文件`(devices/{{target}}/settings.ini)`内的值为参考