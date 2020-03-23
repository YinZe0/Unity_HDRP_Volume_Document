不知道具体对不对，不是专业的摄影人员，这些理论在Unity和Blender中通用  
要使用git lfs下载该项目/文档

# Override
## Exposure
**快速解读: 对光(源)亮度的控制**

1. 光圈数值越小，进(通)光量越大。   
2. 光圈孔径越大, 光圈数值越小。  
3. 越大的光圈, 意味着更浅的景深、更好的背景虚化、达到更加电影感的效果
4. 快门最好保持在帧数的2倍，才会更加自然。  
5. ISO不要走极端,否则会出现越多的噪点,最好使用原生ISO。

Unity 在Mode为Fixed时, Fixed Exposure越高越暗，越低越亮

````
视频地址 ./Video/Exposure 效果示范.mp4
````

`Tips: `   
**1.在Unity中过曝可以使用Tone mapping处理**  
**2.在现实中如果想达到某种情况时仍然过曝可以使用滤镜**

### 链接
[拍视频如何设置相机的快门，光圈和ISO？摄影基础系列教程（3）](https://www.bilibili.com/video/av74937067)  
[还不懂曝光三要素？四分钟带你快速了解光圈、快门ISO以及曝光互易律概念](https://www.bilibili.com/video/av56233641)  
[一学就会的曝光基础](https://www.bilibili.com/video/av20559729)  
[Override-Exposure](https://docs.unity3d.com/Packages/com.unity.render-pipelines.high-definition@7.2/manual/Override-Exposure.html)

## Visual Environment 与 Sky
**快速解读: 对天空盒的设置，Visual Environment可以配合特定Sky使用。**

````
视频地址 ./Video/Visual Environment 与 Sky 效果示范.mp4
````

### 链接
[Override-Visual-Environment](https://docs.unity3d.com/Packages/com.unity.render-pipelines.high-definition@7.2/manual/Override-Visual-Environment.html)  
[Override-Gradient-Sky](https://docs.unity3d.com/Packages/com.unity.render-pipelines.high-definition@7.2/manual/Override-Gradient-Sky.html)  
[Override-HDRI-Sky](https://docs.unity3d.com/Packages/com.unity.render-pipelines.high-definition@7.2/manual/Override-HDRI-Sky.html)  
[Override-Physically-Based-Sky](https://docs.unity3d.com/Packages/com.unity.render-pipelines.high-definition@7.2/manual/Override-Physically-Based-Sky.html)


# Post
## Vignette   (暗角效果 / 晕映)
**快速解读: 在光亮向周围扩散时不断变暗并去饱和度** 

`渐晕是指与中心相比朝向图像边缘变暗和/或去饱和的术语` 

````
视频地址 ./Video/Vignette 效果示范.mp4
````

### 链接
- [Post-Processing-Vignette](https://docs.unity3d.com/Packages/com.unity.render-pipelines.high-definition@7.2/manual/Post-Processing-Vignette.html)


## White Balance
**快速解读: 白平衡准确再现白色的过程，以使你在现实中看到的白色完美呈现至摄像机中。 (以消除影像中不真实的颜色偏差, 例如你拍的照片发黄，则调低白平衡是图片中黄色转为白色展示)**

单位显示为`开尔文`或`K`。数值越小，呈现越偏向于红外光(暖色调)；数值越高，呈现偏向于紫外光(冷色调)。

![颜色变化(图片来自下面首个视频链接)](https://upload-images.jianshu.io/upload_images/16156434-84f76b3f1a67af5a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

图1 | 图2 | 图3 | 图4 | 图5 | 图6 | 图7 
:- | :-: | :-: | :-: | :-: | :-: | -:
2000K | 2800K | 3000K | 4500K | 5600K | 6500K | 8000K
Candle | Tungsten | Tungsten | Fluorescent | Daylight(偏向晴天) | Daylight(偏向阴天) | Moonlight

如果将摄像机的白平衡设置为2000K，则相当于将图1灯源识别为白色，后续的灯源都将向冷色调过渡。

````
视频地址 ./Video/White Balance 效果示范.mp4
````

`Tips: `  
**1.Unity中的温度选项好像与开尔文相反.**   

### 链接
- [白平衡和开尔文色温理论知识](https://www.youtube.com/watch?v=48c02L_nHZc)
- [Post-Processing-White-Balance](https://docs.unity3d.com/Packages/com.unity.render-pipelines.high-definition@7.2/manual/Post-Processing-White-Balance.html)

## Tone mapping
**快速解读: 将HDR(High Dynamic Range)映射到LDR(Low Dynamic Range),使亮度变得在视觉上更加真实。**

`Tips: `  
**1.HDR比普通图片提供更多的动态范围和图像细节**  

### 链接
[基于物理的渲染—HDR Tone Mapping](https://blog.uwa4d.com/archives/Study_HDRToneMapping.html)  
[Tone mapping进化论](https://zhuanlan.zhihu.com/p/21983679)  
[HDR及其应用（tone mapping、bloom）](https://www.jianshu.com/p/8f29baa34bbc)  
[Post-Processing-Tonemapping](https://docs.unity3d.com/Packages/com.unity.render-pipelines.high-definition@7.2/manual/Post-Processing-Tonemapping.html)

## Bloom
**快速解读: 这玩意是辉光，想象一下光照进窗户后在光束周围的一层朦胧的光亮**

Lens Dirt: 这玩意就是糊在镜头上一个Texture

````
视频地址 ./Video/Bloom 效果示范.mp4
````

### 链接
[Post-Processing-Bloom](https://docs.unity3d.com/Packages/com.unity.render-pipelines.high-definition@7.2/manual/Post-Processing-Bloom.html)

## Film Grain
**快速解读: 这玩意是胶片颗粒、噪点**

胶片的颗粒点 数码的噪点  
黑胶的颗粒感 CD的杂音  
这是情怀   
(此话来自[知乎](https://www.zhihu.com/question/38304525/answer/76151272))

````
视频地址 ./Video/Film Grain 效果示范.mp4
````

### 链接
[Post-Processing-Film-Grain](https://docs.unity3d.com/Packages/com.unity.render-pipelines.high-definition@7.2/manual/Post-Processing-Film-Grain.html)

## Motion Blur
**快速解读: 运动模糊，在日常中高帧率拍出的高动态图片(例如:百米跑)可能会出现很不舒服的不连贯性，加上动态模糊使得不连贯的有个好的过渡，让视觉更容易接受**

### 链接
[Post-Processing-Motion-Blur](https://docs.unity3d.com/Packages/com.unity.render-pipelines.high-definition@7.2/manual/Post-Processing-Motion-Blur.html)

## Split Toning
**快速解读: 根据亮度值对图像的不同区域进行着色(亮的地方为高亮，暗的地方为阴影)**

````
视频地址 ./Video/Split Toning 效果示范.mp4
````

### 链接
[Post-Processing-Split-Toning](https://docs.unity3d.com/Packages/com.unity.render-pipelines.high-definition@7.2/manual/Post-Processing-Split-Toning.html)

## Shadows Midtones Highlights
**快速解读: 根据亮度值将图像中的亮度分为三部分【阴影、中间值、高光】, 用以分别对三部分进行准确性的调整。**

````
视频地址 
./Video/Shadows Midtones Highlights 效果示范.mp4
./Video/Shadows Midtones Highlights 去重现Lift Gamma Gain 的效果.mp4
````

### 链接
[Post-Processing-Shadows-Midtones-Highlights](https://docs.unity3d.com/Packages/com.unity.render-pipelines.high-definition@7.2/manual/Post-Processing-Shadows-Midtones-Highlights.html)

## Lift Gamma Gain
**快速解读: 根据亮度值将图像中的亮度分为三部分【Lift、Gamma、Gain】。**

![Lift Gamma  Gain .jpg](https://upload-images.jianshu.io/upload_images/16156434-051f43da5d75569a.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

`【Shadows Midtones Highlights】比【Lift Gamma Gain】高级一点，前者能复现出后者。前者中Midtones没有像后者Gamma一样的过渡，它是根据亮度一刀砍，但根据曲线可以搞出来过渡效果。`

````
视频地址 ./Video/Lift Gamma Gain 效果示范.mp4
````

### 链接
[Post-Processing-Lift-Gamma-Gain](https://docs.unity3d.com/Packages/com.unity.render-pipelines.high-definition@7.2/manual/Post-Processing-Lift-Gamma-Gain.html)

## Lens Distortion
**快速解读: 实现凸透镜与凹透镜效果的画面扭曲**

````
视频地址 ./Video/Lens Distortion 效果示范.mp4
````

### 链接
[Post-Processing-Lens-Distortion](https://docs.unity3d.com/Packages/com.unity.render-pipelines.high-definition@7.2/manual/Post-Processing-Lens-Distortion.html)

## Depth Of Field
**快速解读: 景深的调整，只将目标距离内的事物清晰显示，目标外则进行模糊化处理。**

手动调整模式下需要注意
Near Blur属性中End参数规定的距离`后面`才是`清晰的图景`，Start到End之间的距离内的物体是偏向于模糊的。
Far Blur属性中的Start参数规定的距离`前面`才是`清晰的图景`，Start到End之间的距离内的物体是偏向于模糊的，End之后是彻底模糊的。
**也就是说Near Blur的End到Far Blur的Start之间才是清晰图像，两个Start->End之间都是清晰到模糊的过渡**

````
视频地址 ./Video/Depth Of Field 效果示范.mp4
````

### 链接
[Post-Processing-Depth-of-Field](https://docs.unity3d.com/Packages/com.unity.render-pipelines.high-definition@7.2/manual/Post-Processing-Depth-of-Field.html)

## Color Curves
**快速解读: 控制镜头内颜色的渐变**

````
视频地址 ./Video/Color Curves 效果示范.mp4
````

### 链接
[Post-Processing-Color-Curves](https://docs.unity3d.com/Packages/com.unity.render-pipelines.high-definition@7.2/manual/Post-Processing-Color-Curves.html)

## Color Adjustments
**快速解读: 【颜色校准】 调整最终渲染图像的整体色调，亮度和对比度等内容，可能是用在当其它都设置完成后临时想要进行部分修改使用。**

````
视频地址 ./Video/Color Adjustments 效果示范.mp4
````

### 链接
[Post-Processing-Color-Adjustments](https://docs.unity3d.com/Packages/com.unity.render-pipelines.high-definition@7.2/manual/Post-Processing-Color-Adjustments.html)

## Channel Mixer
**快速解读: Channel Mixer可修改每个输入颜色通道对输出通道整体混合的影响。例如，如果您增加绿色通道对红色通道整体混合的影响，则最终图像中绿色（包括中性/单色）的所有区域的色调都将偏红色。**

RGB: -> Red、Green、Blue
RGBA: -> Red、Green、Blue、Alpha

### 链接
[Post-Processing-Channel-Mixer](https://docs.unity3d.com/Packages/com.unity.render-pipelines.high-definition@7.2/manual/Post-Processing-Channel-Mixer.html)


## Chromatic Aberration (色差)
没什么需要说的

### 链接
[Post-Processing-Chromatic-Aberration](https://docs.unity3d.com/Packages/com.unity.render-pipelines.high-definition@7.2/manual/Post-Processing-Chromatic-Aberration.html)


## Panini Projection
还没搞懂

### 链接
[Post-Processing-Panini-Projection](https://docs.unity3d.com/Packages/com.unity.render-pipelines.high-definition@7.2/manual/Post-Processing-Panini-Projection.html)
