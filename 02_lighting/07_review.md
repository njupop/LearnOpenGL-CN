# 複習

原文     | [Review](http://learnopengl.com/#!Lighting/Review)
      ---|---
作者     | JoeyDeVries
翻譯     | Meow J
校對     | [Geequlim](http://geequlim.com)

恭喜您已經學習到了這個地方！辛苦啦！不知道你有沒有注意到，總的來說我們在學習光照教程的時候學習的並不是OpenGL本身，當然我們仍然學習了一些細枝末節的知識(像訪問uniform數組)。

到現在的所有教程都是關於用一些技巧和公式來操作著色器從而達到真實的光照效果。這同樣向你展示了著色器的威力。

著色器是非常靈活的，你也親眼見證了我們僅僅使用一些3D向量和可配置的變量就能夠創造出驚人的圖形這一點。

在你學過的最後幾個教程中，你學習了有關顏色，馮氏光照模型(包括環境，漫反射，鏡面反射光照)，對象材質，可配置的光照屬性，漫反射和鏡面反射貼圖，不同種類的光，並且學習了怎樣將所有所學知識融會貫通。

記得去實驗一下不同的光照，材質顏色，光照屬性，並且試著利用你無窮的創造力創建自己的環境。

在[下一個教程](http://learnopengl-cn.readthedocs.org/zh/latest/03%20Model%20Loading/01%20Assimp/)當中，我們將加入更高級的形狀到我們的場景中，這些形狀將會在我們之前討論過的光照模型中非常好看。

詞彙表
--------

- **顏色向量(Color Vector)**：一個通過紅綠藍(RGB)分量的組合描繪大部分真實顏色的向量. 一個對象的顏色實際上是該對象不能吸收的反射顏色分量。
- **馮氏光照模型(Phong Lighting Model)**：一個通過計算環境，漫反射，和鏡面反射分量的值來估計真實光照的模型。
- **環境光照(Ambient Lighting)**：通過給每個沒有被光照的物體很小的亮度，使其不是完全黑暗的，從而對全局光照的估計。
- **漫反射著色法(Diffuse Shading)**：光照隨著更多的頂點/片段排列在光源上變強. 該方法使用了法向量來計算角度。
- **法向量(Normal Vector)**：一個垂直於平面的單位向量。
- **正規矩陣(Normal Matrix)**：一個3x3矩陣, 或者說是沒有平移的模型(或者模型觀察)矩陣.它也被以某種方式修改(逆轉置)從而當應用非統一縮放時保持法向量朝向正確的方向. 否則法向量會在使用非統一縮放時失真。
- **鏡面光照(Specular Lighting)**：(sets a specular highlight the closer the viewer is looking at the reflection of a light source on a surface.待翻譯). 鏡面光照是由觀察者的方向，光源的方向和設定高光分散量的反光度值三個量共同決定的。
- **馮氏著色法(Phong Shading)**：馮氏光照模型應用在片段著色器。
- **高氏著色法(Gouraud shading)**：馮氏光照模型應用在頂點著色器上. 在使用很少樹木的頂點時會產生明顯的瑕疵. 會得到效率提升但是損失了視覺質量。
- **GLSL結構體(GLSL struct)**：一個類似於C的結構體，用作著色器變量的容器. 大部分時間用來管理輸入/輸出/uniform。
- **材質(Material)**：一個物體反射的環境，漫反射，鏡面反射光照. 這些東西設定了物體的顏色。
- **光照(性質)(Light(properties)**：一個光的環境，漫反射，鏡面反射的強度. 可以應用任何顏色值並對每一個馮氏分量(Phong Component)都定義一個光源閃爍的顏色/強度。
- **漫反射貼圖(Diffuse Map)**：一個設定了每個片段中漫反射顏色的紋理圖片。
- **鏡面貼圖(Specular Map)**：一個設定了每一個片段的鏡面強度/顏色的紋理貼圖. 僅在物體的特定區域允許鏡面高光。
- **平行光(Directional Light)**：只有一個方向的光源. 它被建模為不管距離有多長所有光束都是平行而且其方向向量在整個場景中保持不變。
- **點光源(Point Light)**：一個場景中光線逐漸淡出的光源。
- **衰減(Attenuation)**：光減少強度的過程，通常使用在點光源和聚光下。
- **聚光(Spotlight)**：一個被定義為在某一個方向上錐形的光源。
- **手電筒(Flashlight)**：一個擺放在觀察者視角的聚光。
- **GLSL uniform數組(GLSL Uniform Array)**：一個數組的uniform值. 就像C語言數組一樣工作，只是不能被動態調用。