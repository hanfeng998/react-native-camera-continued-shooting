# react-native-camera-continued-shooting
本组件是基于react-native-camera@1.0.2版本修改而成，如果是依赖其他版本的react-native-camera直接将Android和iOS对应的原生
代码和src/Camera.js代码移植过去就行了，本组件主要是为了解决react-native-camera前后摄像头拍摄后拼接后的视频旋转角度问题，
### iOS端的修改是集成了视频自动转换（mov转mp4，react-native-camera录制视频默认是mov格式的），以及视频拼接旋转；
### Android端解决了react-native-camera组件在Android端的后置摄像头拍摄后的画面旋转适配问题，Android端不能通过简单的
前后摄像头视频分开旋转拼接，这样的话里面的metadata会丢失而导致旋转属性丢失，所以只能通过处理更底层的frame YUV视频原始数据旋转全部帧，
然后对视频片进行合并得到正向视频播放画面,由于视频处理so依赖比较多相对于其他视频处理sdk动不动就增加18、19M，集成本组件的视频续拍功能
Android端的apk大小仅增加7M左右；
