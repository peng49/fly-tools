#### vue-cli 初始化项目

```shell
# 通过 config 命令切换源
$ npm config set registry https://registry.npm.taobao.org
# 安装cli
$ npm install -g @vue/cli
# 检查是否安装成功
$ vue --version
@vue/cli 5.0.4

# 初始化项目
# https://cli.vuejs.org/zh/guide/creating-a-project.html#vue-create
vue create frontend
cd frontend
npm install element-plus  --save
npm install vue-router  --save
```