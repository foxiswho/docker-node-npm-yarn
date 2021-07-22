# demo
node 14

npm

yarn 1.22

```bash
docker run -it --rm --name node14 -p 4000:4000 foxiswho/node-npm-yarn:14
```
>`/home/app` : Default directory in container
>
> command : node npm yarn vim supervisor wget curl tar zip unzip git
> 
> `yarn dev`: Default start command in container

# 中国镜像

设置淘宝镜像
```bash
yarn config set registry https://registry.npm.taobao.org
```

# demo (in container)

```bash
yarn create vite-app app
cd app
yarn
yarn dev
```

# build
```bash
docker build . -t foxiswho/node:14
```

# 默认案例

```bash
docker run -it --rm --name yarn-demo -p 4000:4000 foxiswho/node-npm-yarn
```

> /home/app : 容器内部项目目录
> 
> 容器默认端口号: 4000
> 
> 访问网址: http://127.0.0.1:4000

## 案例 package 文件配置

package 中 `scripts` 内，必须增加 `"dev": "vite --mode development"` 配置，yarn 默认启动命令为 `yarn dev`

```json
{
  "scripts": {
    "dev": "vite --mode development"
  }
}
```
