# marmotVim
SpaceVim 离线安装脚本

## 离线安装依赖
+ git: 用于下载和更新 SpaceVim 的插件
+ lua: 用于 neocomplete 补全
+ python2/3: 用于 job 特性和部分插件。推荐都安装
+ neovim
+ DejaVu Sans Mono for PowerLine: 用于 SpaceVim 的插件
+ Offline plugins package: SpaceVim 的插件
+ SpaceVim
+ pynvim 
+ cscope

## 离线安装(需要root权限)

### 1. 安装nenvim

```bash
git clone https://github.com/neovim/neovim
cd neovim/
make
sudo make install
sudo mv /usr/bin/vim /usr/bin/vim~
sudo ln -s /usr/local/bin/nvim /usr/bin/vim
vim --version # 输出 NVIM v0.5.0-dev 说明安装成功
```

### 2. 安装依赖

```bash
pip install --user --upgrade pynvim # neovim python插件依赖

# python layer依赖，参考博客：https://blog.csdn.net/weixin_30471065/article/details/98710992?utm_medium=distribute.pc_aggpage_search_result.none-task-blog-2~all~first_rank_v2~rank_v25-8-98710992.nonecase
pip install --user flake8
pip install --user yapf
pip install --user autoflake
pip install --user isort
pip install jedi
```

### 3. 安装 SpaceVim

```bash
sudo yum -y install git-lfs
git clone https://github.com/marmotedu/marmotVim
cd marmotVim
git lfs install
git lfs track *.tgz
rm *.tgz
git checkout -- .
./marmotVimCtl install
```

### 4. 卸载 Spacevim

```bash
./marmotVimCtl uninstall
```

## FAQ
