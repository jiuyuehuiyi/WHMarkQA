# 文档目录

- [git](#git)
    - [查看本地tag](#查看本地tag)
    - [添加本地tag](#添加本地tag)
    - [将tag传到远程](#将tag传到远程)
    - [删除本地tag](#删除本地tag)
    - [删除远程标签](#删除远程标签)
    - [查看本地分支](#查看本地分支)
    - [查看远程分支](#查看远程分支)
    - [创建分支](#创建分支)
    - [切换分支](#切换分支)
        
- [pod](#pod)
    - [注册Trunk](#注册Trunk)
    - [创建spec文件](#创建spec文件)
    - [验证spec文件](#验证spec文件)
    - [获取MIT文件](#获取MIT文件)
    - [发布podspec](#发布podspec)
    - [删除已发布的podspec](#删除已发布的podspec)
    - [创建CocoaPods库的模板](#创建CocoaPods库的模板)
    - [创建一个私有库索引并添加到本地](#创建一个私有库索引并添加到本地)
    - [查看是否添加成功](#查看是否添加成功)
    - [向Repo提交podspec](#向Repo提交podspec)
    
- [常见问题](#常见问题)
   - [1. unable to find a pod with name, author, summary, or description matching `XXX`](#1-unable-to-find-a-pod-with-name-author-summary-or-description-matchingxxx)
   - [2. pod 'Realm' 在执行pod install --verbose 卡住在 downloading dependency: sync `XXX` from …](./PodQA/2.md)
   - [3.修改极光官网应用中的 BundleID 或包名](https://community.jiguang.cn/t/topic/5145/29)
   - [4.Xcode 清理存储空间](./OtherQA/O1.md)
   - [5.mp3转caf]()

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

## 查看本地分支
git branch

## 查看远程分支
git branch -r

## 创建分支
git branch `<分支名>`

## 切换分支
git checkout `<分支名>`


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

## 删除已发布的podspec
pod trunk delete `XXX.podspec`

## 创建CocoaPods库的模板
pod lib create `XXX`

## 创建一个私有库索引并添加到本地
pod repo add localSpec `私有库索引仓库`

## 查看是否添加成功
pod repo

## 向Repo提交podspec
pod repo push localSpec `XXX.podspec`

# 常见问题

## 1. unable to find a pod with name, author, summary, or description matching `XXX`

Step:
1. rm ~/Library/Caches/CocoaPods/search_index.json
2. pod setup

## 5.mp3转caf
afconvert input output -d ima4 -f caff -v

* afconvert 音频转换指令
* -f adts 指定文件格式:acc格式音频需要指定为adts(文件与格式化格式见上面帮助信息)
* -d acc 指定数据格式
* input.wav 待转换文件名称

```
Audio file and data formats:
'3gpp' = 3GP Audio (.3gp)
           data_formats: 'Qclp' 'aac ' 'aace' 'aacf' 'aach' 'aacl' 
                         'aacp' 'samr' 
'3gp2' = 3GPP-2 Audio (.3g2)
           data_formats: 'Qclp' 'aac ' 'aace' 'aacf' 'aach' 'aacl' 
                         'aacp' 'samr' 
'adts' = AAC ADTS (.aac, .adts)
           data_formats: 'aac ' 'aach' 'aacp' 
'ac-3' = AC3 (.ac3)
           data_formats: 'ac-3' 
'AIFC' = AIFC (.aifc, .aiff, .aif)
           data_formats: I8 BEI16 BEI24 BEI32 BEF32 BEF64 UI8 'ulaw' 
                         'alaw' 'MAC3' 'MAC6' 'ima4' 'QDMC' 'QDM2' 
                         'Qclp' 'agsm' 
'AIFF' = AIFF (.aiff, .aif)
           data_formats: I8 BEI16 BEI24 BEI32 
'amrf' = AMR (.amr)
           data_formats: 'samr' 'sawb' 
'm4af' = Apple MPEG-4 Audio (.m4a, .m4r)
           data_formats: 'aac ' 'aace' 'aacf' 'aach' 'aacl' 'aacp' 
                         'ac-3' 'alac' 'ec-3' 'paac' 'pac3' 'qec3' 
                         'zec3' 
'm4bf' = Apple MPEG-4 AudioBooks (.m4b)
           data_formats: 'aac ' 'aace' 'aacf' 'aach' 'aacl' 'aacp' 
                         'paac' 
'caff' = CAF (.caf)
           data_formats: '.mp1' '.mp2' '.mp3' 'QDM2' 'QDMC' 'Qclp' 
                         'Qclq' 'aac ' 'aace' 'aacf' 'aach' 'aacl' 
                         'aacp' 'ac-3' 'alac' 'alaw' 'dvi8' 'ec-3' 
                         'ilbc' 'ima4' I8 BEI16 BEI24 BEI32 BEF32 
                         BEF64 LEI16 LEI24 LEI32 LEF32 LEF64 'ms\x00\x02' 
                         'ms\x00\x11' 'ms\x001' 'paac' 'pac3' 'pec3' 
                         'qaac' 'qac3' 'qach' 'qacp' 'qec3' 'samr' 
                         'ulaw' 'zaac' 'zac3' 'zach' 'zacp' 'zec3' 
'ec-3' = EC3 (.ec3)
           data_formats: 'ec-3' 
'MPG1' = MPEG Layer 1 (.mp1, .mpeg, .mpa)
           data_formats: '.mp1' 
'MPG2' = MPEG Layer 2 (.mp2, .mpeg, .mpa)
           data_formats: '.mp2' 
'MPG3' = MPEG Layer 3 (.mp3, .mpeg, .mpa)
           data_formats: '.mp3' 
'mp4f' = MPEG-4 Audio (.mp4)
           data_formats: 'aac ' 'aace' 'aacf' 'aach' 'aacl' 'aacp' 
                         'ac-3' 'ec-3' 'qec3' 'zec3' 
'NeXT' = NeXT/Sun (.snd, .au)
           data_formats: I8 BEI16 BEI24 BEI32 BEF32 BEF64 'ulaw' 
'Sd2f' = Sound Designer II (.sd2)
           data_formats: I8 BEI16 BEI24 BEI32 
'WAVE' = WAVE (.wav)
           data_formats: UI8 LEI16 LEI24 LEI32 LEF32 LEF64 'ulaw' 
                         'alaw' 
```
