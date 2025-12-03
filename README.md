# Picgo+Github+Typora图床

## 1.安装picgo

### 1.1下载并安装Node.js

首先需要安装Node.js，新版Node.js使用npm无法安装picgo，改用yarn安装。

在官网下载安装包，如果载下载时选择了yarn版，则无需执行1.2安装yarn

![image-20251203191320036](https://cdn.jsdelivr.net/gh/Darkstar-s/pictures/Markdown/202512/03191320_33e-image-20251203191320036.png)

### 1.2安装yarn

使用npm安装yarn

```
npm install -g yarn
```

### 1.3使用yarn安装picgo

```
yarn global add picgo
```

## 2.配置picgo

### 2.1新建Github仓库

必须设置为公开仓库

![image-20251203193823700](https://cdn.jsdelivr.net/gh/Darkstar-s/pictures/Markdown/202512/03193824_560-image-20251203193823700.png)

### 2.2申请Github访问token

如下图所示新建token

![image-20251203190719837](https://cdn.jsdelivr.net/gh/Darkstar-s/pictures/Markdown/202512/03192626_0fc-03190720_72d-image-20251203190719837.png)

### 2.3修改配置文件

配置文件config.json在"‪C:\\用户名\\ZC\\.picgo"目录下，模板如下

```
{
  "picBed": {
    "uploader": "github",
    "current": "github",
    "github": {
      "repo": "Darkstar-s/pictures",
      "branch": "main",
      "token": "ghp_xxx",
      "path": "Markdown/",
      "customUrl": "https://cdn.jsdelivr.net/gh/Darkstar-s/pictures"
    },
    "transformer": "path"
  },
  "picgoPlugins": {
    "picgo-plugin-github-plus": true,
    "picgo-plugin-rename-file": true
  },
  "picgo-plugin-rename-file": {
    "format": "{y}{m}/{d}{h}{i}{s}_{rand:3}-{origin}",
    "enable": true
  }
}
```

### 2.4picgo安装插件（可选）

> [!TIP]
>
> 将picgo添加至系统环境变量PATH中，在PATH中添加以下路径
>
> ```
> C:\用户名\ZC\AppData\Local\Yarn\bin
> ```

安装github增强插件`github-plus`

```
picgo install github-plus
```

安装重命名插件`rename-file` ，可以帮我们按照一定的规则将文件进行重命名

```
picgo install rename-file
```

## 3.Typora使用picgo

在设置中找到图像，“插入图片时“操作改成**上传图片**，上传服务设定中上传服务下选择**自定义命令**，命令为

```
picgo upload
```

![image-20251203192346876](https://cdn.jsdelivr.net/gh/Darkstar-s/pictures/Markdown/202512/03192347_cdf-image-20251203192346876.png)

点击测试图片上传，如果搭建成功，会返回有效的图片链接，在Github图床仓库中也可以看到上传的图片。

至此，完成图床的搭建和使用。