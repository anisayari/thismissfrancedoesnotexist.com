{% assign image_files = site.static_files %}

{% assign paths = image_files | map: "path" %}

<img id="face">

<div id="description" class="show">



<p>Imagined by a GAN (<a href="https://en.wikipedia.org/wiki/Generative_adversarial_network">generative adversarial network)</a>
</p>

<p>
<a href="https://arxiv.org/abs/1912.04958">StyleGAN2</a>
<span>(Dec 2019)</span> -
<a href="https://research.nvidia.com/person/tero-karras">Karras</a> et al. and Nvidia</p><p>Don't panic. Learn how it works
<a href="https://www.youtube.com/watch?v=u8qPvzk0AfY" target="_blank">[1]</a>
<a target="_blank" href="https://www.youtube.com/watch?v=dCKbRCUyop8">[2]</a>
<a target="_blank" href="https://www.youtube.com/watch?v=SWoravHhsUU">[3]</a>
</p>

<p>Code for training your own</p>
<a href="https://github.com/NVlabs/stylegan2">[original]</a>

<a href="https://lucidrains.github.io/">Contact me</a> <!-- &bull; <a href="https://thischemicaldoesnotexist.com">Molecules</a> | <a href="https://thisarticledoesnotexist.com">News</a> | <a href="https://thispersondoesnotexist.com/friends">Friends</a> | <a href="https://thispersondoesnotexist.com/office">Office</a>-->
</p>

</div>

<script>
  var myVar = '{{ paths }}';
  var array = myVar.split("assets/");
  array = array.filter(element => element.includes('fakes'))
  //array = array.replace('.png/','.png');

  //array = array.replace(element => element.replace('.png/','.png'))
  array = array.map(path => path.replace('image', 'assets/image'))
  array = array.map(path => path.replace('.png/','.png'))

  //array = array.replace('image','assets/image');
  console.log(array)

  document.getElementById("face").src=array[Math.floor(Math.random()*array.length)]
</script>
