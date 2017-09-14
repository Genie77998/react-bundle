# 安装
```
npm i vp-bundle --save
```


# 使用

```
import loadComponent from 'vp-bundle'

import Reg from 'bundle-loader?lazy&name=reg!./containers/Reg'

<Route path="/reg" component={loadComponent(Reg)} />

```
# 说明及注意事项

已经内置bundel-loader依赖

import Reg from 'bundle-loader?lazy&name=reg!./containers/Reg'

name后面的值是按需加载的文件名 在webpack配置里面会用到
!后面是组件的路径
    
```
    output: {
        chunkFilename: 'static/js/[name].[chunkhash:8].js',
    }
```

按需加载的文件在服务端渲染的时候要将文件样式抽离 
ExtractTextPlugin 设置allChunks属性为true

```
    new ExtractTextPlugin({
      filename: 'style.[contenthash:8].css',
      allChunks: true
    })
```


