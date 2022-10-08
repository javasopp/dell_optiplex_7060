# dell_optiplex_7060
Dell Optiplex 7060 的黑苹果引导

> 说明
>
> Dell 7060系列 Mac OS 13 Ventura系列引导，可用于10、11、12各版本。

## 本机配置

Dell Optiplex 7060 

- 系统版本: macOS 13.0 beta 8
- Opencore 版本: 0.8.5
- CPU: i7-8700
- 主板: Dell OptiPlex Q370
- 内存: 金士顿马甲条 4*16 ddr4 2666
- 显卡: Intel UHD Grahpics 630 2048MB
- 网卡: 仅有有线网卡
- 硬盘 普通的m2硬盘

## 主要功能

- 没有插装网卡，除开无线功能，其他所有功能都完美，包括风扇转速控制。
- 如果需要无线，请自行淘宝购买免驱卡插上即可。

## 必须执行的操作

需要在grub中执行以下命令(本efi中已经存在对应的grub shell了):

- setup_var 0x8DC 0x2（修改dvmt 为64MB，只适合dell 7060, 其他机器请自行查找）
- setup_var 0x5BE 0x0（禁用CFG lock，重置bios需要重新执行两条命令）



## BIOS必须的操作

- System Configuration → SATA Operation: ***AHCI***
- Secure Boot → Secure Boot Enable: ***Disabled***
- Security → PPT(TPM) → ***Disabled***
- System Configuration → Serial Port→ ***Disabled***
- Intel® Software Guard Extensions™ → Intel® SGX™ → ***Disabled***
