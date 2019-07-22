# 文档目录

- [git](#git)
    - [查看本地tag](#查看本地tag)
    - [添加本地tag](#添加本地tag)
    - [将tag传到远程](#将tag传到远程)
    - [删除本地tag](#删除本地tag)
    - [删除远程标签](#删除远程标签)
        
- [pod](#pod)
    - [注册Trunk](#注册Trunk)
    - [创建spec文件](#创建spec文件)
    - [验证spec文件](#验证spec文件)
    - [获取MIT文件](#获取MIT文件)
    - [发布podspec](#发布podspec)


# git
## 查看本地tag
git tag

## 添加本地tag
git tag -a `标签名` -m '`注释`'

## 将tag传到远程
git push origin --tags

## 删除本地tag
git tag -d `标签名`

## 删除远程标签
git push origin :refs/tags/`标签名`

# pod

## 注册Trunk
pod trunk register `邮箱` '`用户名`' --description='`描述`'

## 创建spec文件
pod spec create `xxxx`(项目名称/例如Masonry这种)

## 验证spec文件
pod spec lint XXXX.podspec --verbose

## [获取MIT文件](https://choosealicense.com)<br />

## 发布podspec
pod trunk push `XXX.podspec`

pod trunk push `XXX.podspec`--allow-warnings

提交后可在[Specs仓库搜索](https://github.com/CocoaPods/Specs),如果能够搜索到说明提交成功

# 常见问题

## unable to find a pod with name, author, summary, or description matching `XXX`

Step:
1. rm ~/Library/Caches/CocoaPods/search_index.json
2. pod setup