# MIP Mapping

**MIP mapping** \(also sometimes spelled as mipmapping\) is a technique where an original high-resolution texture map is scaled and filtered into multiple resolutions within the texture file. MIP maps can be automatically generated from the original texture, but may also be individually painted or adjusted by the texture artist. Typically each subsequent MIP level is half the size of the previous, which guarantees that the complete texture \(the original and its MIP maps\) is no greater than 1.5 times the original texture.

{% hint style="info" %}
MIP comes from the Latin, multum in parvo, meaning a multitude in a small space.
{% endhint %}

Each scaled texture, or MIP level, represents what the texture would look like at a specific distance from the users viewpoint. Through the use of filters, the MIP levels give a more natural representation of how colors and details tend to blend together when viewed at a distance.

The main purpose of this technique is to maintain texture definition on surfaces further from the camera and to avoid unslightly [moiré patterns](http://en.wikipedia.org/wiki/moir%C3%A9_pattern) which can appear on surfaces, especially as they approach an angle parallel to the axis of the camera. Since the MIP maps are generated in advance, this technique trades a modest increase in texture memory usage to achieve a significant increase in visual quality, avoiding costly real-time calculations that might otherwise be used to solve the problem.

{% hint style="info" %}
**Source:** [https://developer.valvesoftware.com/wiki/MIP\_Mapping](https://developer.valvesoftware.com/wiki/MIP_Mapping)  
**Reference:** 

* [Mipmap](http://en.wikipedia.org/wiki/Mipmap) - a Wikipedia article on the subject.
* [Mip-Mapping in Direct3D](http://www.gamedev.net/reference/articles/article1233.asp) - a GameDev.net article.
* [Texture Filtering](http://en.wikipedia.org/wiki/Texture_filtering) a Wikipedia article about common resampling and interpolation methods.
{% endhint %}

