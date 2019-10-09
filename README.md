## 介绍
- platform-plus-ui基于vue、element-ui构建开发，实现platform-plus后台管理前端功能。
- 封装富文本编辑器组件，并且支持使用v-model双向绑定富文本数据。简单到像使用input一样。
```
<ueditor v-model="msg"></ueditor>
...
data () {
      return {
        msg: '<h2><img src="http://img.baidu.com/hi/face/i_f03.gif"/>Vue + UEditor + v-model双向绑定</h2>'
      }
```
- 后台地址：https://gitee.com/fuyang_lipengjun/platform-plus

## 实现功能
```
- 系统管理
    - 菜单管理
    - 组织机构
    - 系统参数
    - 字典管理
    - 文件上传
    - 系统日志
- 权限管理
    - 管理员列表
    - 角色管理
- 短信平台
    - 短信配置
- 任务调度
    - 定时任务
- 开发工具
    - 在线用户管理
    - 缓存信息
    - SQL监控
    - 接口文档
    - 代码生成器
```

# 技术栈
你需要在本地安装 nodejs。

- [nodejs](http://nodejs.org/)
- [ES6](http://es6.ruanyifeng.com/)
- [vue-cli](https://github.com/vuejs/vue-cli)
- [vue](https://cn.vuejs.org/index.html)
- [vue-router](https://github.com/vuejs/vue-router)
- [vuex](https://github.com/vuejs/vuex)
- [axios](https://github.com/axios/axios)
- [vue-cookie](https://github.com/alfhen/vue-cookie)
- [element-ui](https://github.com/ElemeFE/element)
- [iconfont](http://www.iconfont.cn/)

# 目录结构
本项目已经通过vue-cli脚手架为你生产完整的开发框架（有根据业务需求做调整修改），下面是整个项目的目录结构。
```bash
├── build                      // 构建相关  
├── config                     // 构建配置相关
├── dist                       // 构建打包生成部署文件
│   ├── 1902151513             // 静态资源（19年02月15日15时13分）
│   ├── config                 // 配置
│   ├── index.html             // index.html入口
├── src                        // 源代码
│   ├── assets                 // 静态资源
│   ├── components             // 全局公用组件
│   ├── element-ui             // element-ui组件配置
│   ├── element-ui-theme       // element-ui组件主题配置
│   ├── icons                  // 所有 svg icons
│   ├── router                 // 路由
│   ├── store                  // 全局 store管理
│   ├── utils                  // 全局公用方法
│   ├── views                  // view
│   ├── App.vue                // 入口组件
│   ├── main.js                // 入口
├── static                      // 第三方不打包资源
│   ├── config                 // 全局变量配置
│   ├── img                    // favicon图标
│   ├── plugins                // 插件
├── .babelrc                   // babel-loader 配置
├── eslintrc.js                // eslint 配置项
├── .gitignore                 // git 忽略项
├── index.html                 // html模板
└── package.json               // package.json
```

# 安装
```bash
# 安装依赖
npm install

# 启动服务
npm run dev
```

安装过程中，可能会出现安装过慢、报错等情况，请尝试以下方式：
```bash
npm install -g cnpm --registry=https://registry.npm.taobao.org

cnpm install

# 启动服务
npm run dev
```
启动完成后会自动打开浏览器访问 [http://localhost:8000]()。

# 打包部署
```
修改
/static/config/index-[prod].js文件中  
window.SITE_CONFIG['baseUrl'] = 'http://ip/platform-admin'// 后台接口请求地址
window.SITE_CONFIG['domain'] = '静态资源cdn地址';  

# 构建生产环境(默认)
npm run build

```
# 部署Nginx配置参考
```
  location / {
        # 指向我们打包后上传的前端文件
        root /usr/local/nginx/dist;
        index index.html;
    }
    location /platform-admin {
        # 转发请求到后端
        proxy_pass                         http://localhost:8801;
        proxy_set_header  Host             $host;
        proxy_set_header  X-Real-IP        $remote_addr;
        proxy_set_header  X-Forwarded-For  $proxy_add_x_forwarded_for;
    }
```

**项目演示**
- 演示地址：http://fly2you.cn/platform-plus/#/login
- 账号密码：
  - admin/admin
  - test/888888
  - test1/888888
  - test2/888888
  - test3/888888
  - test4/888888
  - test5/888888
  - test6/888888
  - test7/888888
  - test8/888888
  - test9/888888
  - test10/888888

**效果图：**
- 菜单管理
![https://platform-wxmall.oss-cn-beijing.aliyuncs.com/upload/platform-plus/platform-plus.jpg](https://platform-wxmall.oss-cn-beijing.aliyuncs.com/upload/platform-plus/platform-plus.jpg "菜单管理")
- 字典管理
![https://platform-wxmall.oss-cn-beijing.aliyuncs.com/upload/platform-plus/dict.png](https://platform-wxmall.oss-cn-beijing.aliyuncs.com/upload/platform-plus/dict.png "字典管理")
- 在线人数
![https://platform-wxmall.oss-cn-beijing.aliyuncs.com/upload/platform-plus/users.png](https://platform-wxmall.oss-cn-beijing.aliyuncs.com/upload/platform-plus/users.png "在线人数")
- 缓存数据
![https://platform-wxmall.oss-cn-beijing.aliyuncs.com/upload/platform-plus/doc.png](https://platform-wxmall.oss-cn-beijing.aliyuncs.com/upload/platform-plus/redis.png "缓存数据")
- 接口文档
![https://platform-wxmall.oss-cn-beijing.aliyuncs.com/upload/platform-plus/doc.png](https://platform-wxmall.oss-cn-beijing.aliyuncs.com/upload/platform-plus/doc.png "接口文档")

#### 提交反馈
1. 欢迎提交 issue，请写清楚遇到问题的原因，开发环境，复显步骤。
2. 不接受`功能请求`的 issue，功能请求可能会被直接关闭。  
3. 代码修改请遵循指定的 `ESLint` 规则，`PR` 之前请先执行 `npm run lint` 进行代码风格检测，大部分语法细节可以通过 `npm run fix` 修正。
4. 官方QQ群：
- <a target="_blank" href="//shang.qq.com/wpa/qunwpa?idkey=ac742b7481b95fac926a3f2196085108bceeebcdf14bd716cbea519751e69445"><img border="0" src="http://pub.idqqimg.com/wpa/images/group.png" alt="微同软件 ①群" title="微同软件 ①群"></a>
- <a target="_blank" href="//shang.qq.com/wpa/qunwpa?idkey=dcb460bfa21213a2712677bab7292fd8eb2138a1914af5af397b58e7c02690c5"><img border="0" src="http://pub.idqqimg.com/wpa/images/group.png" alt="微同软件 ②群" title="微同软件 ②群"></a>
- <a target="_blank" href="//shang.qq.com/wpa/qunwpa?idkey=c7657db5d4e65a40e46ee5998534f7b9b9fa56d0347c3af3157c7f6240c0d0dd"><img border="0" src="http://pub.idqqimg.com/wpa/images/group.png" alt="微同软件 ③群" title="微同软件 ③群"></a>

#### 常用API
- [Vue](https://cn.vuejs.org/v2/api/)
- [element-ui](http://element-cn.eleme.io/#/zh-CN/component/installation)
- [echarts](https://www.echartsjs.com/api.html#echarts)
- [iconfont](https://www.iconfont.cn/search/index)
