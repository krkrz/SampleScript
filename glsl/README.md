# GLSLシェーダー

サンプルに置いているが、実際に使用するためのシェーダースクリプト。  
OpenGL ES2.0 で動くように GLSL ES1.0。  
通常描画は組み込みだが、クロスフェードやユニバーサルトランジションはトランジションで実使用する。  
トランジションで使用するシェーダーは0～255ではなく、0.0～1.0を指定する用になっている。  
ユニバーサルトランジションのvague値も255で割った値、デフォルトを依然と同じにするなら(real)64/255.0となる。  
トランジションシェーダーでは、0.0と1.0の時に片方の画像をそのまま表示する形にはなっていない。  
呼び出し側で最初(0.0)は開始時の画像を、終了時(1.0)は次の画像をそのまま表示するようにする。  

* alphaclip.frag  
通常画像をアルファのみを持ったテクスチャでマスクするフラグメントシェーダー。
* crossfade.frag  
背景不透明時のクロスフェード用フラグメントシェーダー。
* crossfade_a.frag  
背景透過時のクロスフェード用フラグメントシェーダー。
* default.frag  
通常描画用フラグメントシェーダー、組み込みのデフォルトと同じなので使う機会はない。
* default.vert  
デフォルトバーテックスシェーダー、組み込みのデフォルトと同じだが、他のフラグメントシェーダーと組み合わせて使う。
* gamma.frag  
ガンマ補正フラグメントシェーダー。
* grayscale.frag  
グレースケール変換フラグメントシェーダー。
* negative_positive_reversal.frag  
ネガポジ反転フラグメントシェーダー。
* universal.frag  
ユニバーサルトランジション用フラグメントシェーダー、背景不透明用。
* universal_a.frag    
ユニバーサルトランジション用フラグメントシェーダー、背景透過用。
* universal_v512.frag  
ユニバーサルトランジション用フラグメントシェーダー、vague値が512以上、背景不透明用。
* universal_v512_a.frag  
ユニバーサルトランジション用フラグメントシェーダー、vague値が512以上、背景透過用。
