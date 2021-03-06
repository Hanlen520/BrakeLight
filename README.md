# BrakeLight [![Build Status](https://travis-ci.org/KennethYo/BrakeLight.svg?branch=master)](https://travis-ci.org/KennethYo/BrakeLight) [![CircleCI](https://circleci.com/gh/KennethYo/BrakeLight/tree/master.svg?style=svg)](https://circleci.com/gh/KennethYo/BrakeLight/tree/master)

Brake Light 中文意思是刹车灯，当集成到 Android 应用中，测试时发生 crash ，会在通知栏显示一条消息，点击消息显示 crash 信息，极大方便了测试同学把 crash 的信息传递给开发同学。

![演示图片](ezgif.com-video-to-gif.gif)

# Download

```groovy
dependencies {
    debugCompile 'me.kennethyo.library:brakelight:latest.version'
    releaseCompile 'me.kennethyo.library:brakelight-no-op:latest.version'
}
```

# Compile

```java
public class MyApplication extends Application {

  private static MyApplication instance;

  public static MyApplication getInstance() {
    return instance;
  }

  private BrakeLightWatch watch;

  @Override public void onCreate() {
    super.onCreate();
    instance = this;
    watch = BrakeLight.install(this);
  }

  public BrakeLightWatch getWatch() {
    return watch;
  }
}
```

# Todo

- ~~简化集成，`UncaughtExceptionHandler`移入 Library.~~
- 系统分享，增加文件方式.
- crash 信息列表.
- 支持文件选择器打开报错文件.
- 支持消息通知振动和铃声.

# License

```
Copyright 2017 Kenneth Yo

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```
