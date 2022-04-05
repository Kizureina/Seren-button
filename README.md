# Rina Button

Rina button [点此前往 https://rinabutton.a1ex.pw](https://rinabutton.a1ex.pw)

[![Deploy GitHub Pages](https://github.com/A1exMinatoooo/rina-button/actions/workflows/main.yml/badge.svg)](https://github.com/A1exMinatoooo/rina-button/actions/workflows/main.yml)

相关链接：

* [林莉奈 - Bilibili](https://space.bilibili.com/1243266187/)

## 如何贡献

请 Fork 此分支，并在修改完成后提交 Pull Request，审核通过后将会合并。

### 添加或编辑声音

**概述**: 所有的音频元数据均存放在 [src/voices.json](src/voices.json)。若要修改这些音频，您需要修改此文件。

音频文件应以 `mp3` 或 `m4a` 格式存放在 [public/voices](public/voices) 目录下。对应的请求路径为 `voices/`。

若要添加新音频，请使用 `MP3GainGUI` 等软件对音频进行标准化。目前所有音频均标准化至 80。

本站除 `index.html` 之外均采用强缓存策略。相同文件名的文件即便发生修改也**不会**被客户端主动刷新。因此，无论是新增还是修改已有音频，请**一定**使用与之前不同的文件名。

若您修改了音频文件，请在修改之后删除旧文件。

#### 添加方式

1. 将音频存放在 [public/voices](public/voices) 目录下，并按照 `分类编号 + 3 位数字` 的形式进行命名。

2. 编辑 [src/voices.json](src/voices.json)，在对应分类的 `voiceList` 下添加新项，`name` 为 `分类编号 + 3 位数字`，`path` 为 `name` 加上文件扩展名，`description` 下添加对应的名称及翻译，若不确定翻译可暂时使用原文进行占位。

3. 提交 Pull Request。

### 参与本地化

欢迎有志之士参与本站英语及日语的本地化工作！

主程序的语言文件以语言名称存放在 [src/locales](src/locales) 的三个 `.js` 文件中。

音频文件的翻译存放在 [src/voices.json](src/voices.json)。

对应修改将会自动被程序识别并应用。

## 本地部署开发环境

> 获取本项目最新开发文档请前往[夸按钮 Aqua Button](https://github.com/zyzsdy/aqua-button)。

本站使用 Vue + jQuery + Bootstrap 3。

部署本地环境，首先请安装 Node 最新的 **LTS** 版本。然后进行如下操作：

1. 将代码 clone 到本地。

2. 进入代码目录下并进行 `npm install`。

3. 运行 `npm run serve`。在修改代码的过程中，本地服务器可以实时将您的修改进行编译并呈现。

4. 若需要编译生产环境所使用的的文件，请运行 `npm run build`，该命令将生成 `dist` 目录。本站为纯静态网站，您可以直接将 `dist` 目录作为站点目录部署。

> 您可以在不需要本地编译的前提下为本项目进行贡献，除非您对网站结构作出了更改，此时请先在本地进行测试运行，通过测试并推送到 GitHub 之后，您方可提交 Pull Request 至本项目。

## LICENSE

本项目程序遵守 MIT 协议进行分发。

本项目音频文件遵守 LepusLive 二创协议进行使用。

本项目为粉丝出于个人兴趣爱好创立，与 LepusLive 无任何关联。

## 特别感谢

本项目基于[夸按钮 Aqua Button](https://github.com/zyzsdy/aqua-button) 进行二次开发，感谢原开发者 [Ted Zyzsdy](https://github.com/zyzsdy)。

感谢为本项目作出贡献的所有人。