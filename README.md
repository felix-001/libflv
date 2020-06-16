# Feature
H264和AAC封装为flv

# How to use
- 创建实例
```
FLVContext *FLVNewContext( FLVParam *param )
```
FLVParam:  
字段 | 说明
---|---
videocodec | 视频编码格式
audiocodec | 音频编码格式
samplerate | 音频采样率
samplesize | 音频采样位宽
soundtype | 声道个数
opaque | 用户自定义参数
write_packet | flv tag 回调

- 写入音视频数据
```
int FLVWriteAVData( FLVContext *ctx, FrameInfo *frame )
```
FrameInfo:  
字段 | 说明
---|---
data | 音频或视频数据
len  | 数据长度
timestamp | 时间戳
type | 媒体类型
iskey | 是否为关键帧(媒体类型为视频时)

- 刷新缓冲buffer
```
int FLVFlush( FLVContext *ctx );
```

- 销毁实例
```
int FLVDestroyContext( FLVContext *ctx );
```

# 关于作者
treeswayinwind@gmail.com
