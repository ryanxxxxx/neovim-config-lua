# neovim-config-lua配置使用
# 前提条件：

1. 已安装python和golang环境
2. 已安裝 neovim
3. 若已配置 neovim，请执行以下操作：

```bash
#备份配置文件：
cp ~/.config/nvim{,.bk}
cp ~/.local/share/nvim{,.bk}
```

+ 下载配置文件
```bash
git clone https://github.com/ryanxxxxx/neovim-config-lua.git
```

+ 复制配置文件到 ~/.config 目录
```bash
cp -r ./neovim-config-lua/config/nvim ~/.config/
```

+ 修改用户目录
```bash
mv ~/.config/nvim/lua/x ~/.config/nvim/lua/$USER
```

+ nvim-tree.lua 文件
```bash
# -a. macOS系统，重命名文件 "nvim-tree.lua.macOS" 为 nvim-tree.lua
# -b. Linux系统，重命名文件 "nvim-tree.lua.Linux" 为 nvim-tree.lua
cd ~/.config/nvim/lua/$USER/plugins/
mv nvim-tree.lua.macOS nvim-tree.lua
```

+ 安装插件前，需要修改 init.lua 文件的插件路徑
```bash
sed -i "s/x./${USER}./g" ~/.config/nvim/init.lua
```

> 修改路径， `x` 修改为当前用户名，与上述路径保持一致 ~/.config/nvim/lua/$USER/plugins/
require("x.plugins-setup")

+ 啟動 nvim 安裝插件(需要等待安裝完成再操作)
```bash
nvim
```

+ 查看 lsp 安装情况
```bash
#進入 nvim
nvim
#輸入 :Mason 查看插件安裝情況
:Mason
```
