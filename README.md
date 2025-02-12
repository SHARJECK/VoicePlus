【夏杰语音】
语音数据对接api使用说明。
语音录音数据传输识别，音频数据格式PCM 16bit 16KHz

#可用于语音遥控器插件对接，采集语音遥控器数据并解码为pcm，通过该sdk的api发送给夏杰语音，实现语音识别。
====================================
【权限要求】
需要开启网络访问权限
====================================

1、初始化实例
import com.sharjeck.voiceplus.aimic.AudioTransfer;

AudioTransfer mAudioTransfer = AudioTransfer.getInstance();

    //设置国内版语音软件
    mAudioTransfer.setType(1);

    //设置国外版语音软件(不设置的话，默认为国际版)
    mAudioTransfer.setType(0);

2、启动服务
mAudioTransfer.startTransfer();


3、语音开始采集
mAudioTransfer.voiceKeyDown(this);


4、发送数据
mAudioTransfer.send(byte[] buffer, int length);
可以连续调用

5、语音采集结束
mAudioTransfer.voiceKeyUp(this);


6、停止服务
mAudioTransfer.stopTransfer();
