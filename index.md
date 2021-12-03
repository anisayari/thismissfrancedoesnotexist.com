{% assign image_files = site.static_files %}

{% assign paths = image_files | map: "path" %}

<img id="face">

<div id="description" class="show">


<p> Developped by <a href="https://twitter.com/DFintelligence">Defend Intelligence</a>. Check my Youtube channel<a href="https://www.youtube.com/c/defendintelligence-tech"> here </a>.
</p>
<p>Imagined by a GAN (<a href="https://en.wikipedia.org/wiki/Generative_adversarial_network">generative adversarial network)</a>
</p>
<p>
Using <a href="https://arxiv.org/abs/1912.04958">StyleGAN2</a> <span>(Dec 2019)</span> -
<a href="https://research.nvidia.com/person/tero-karras">Karras</a> et al. and Nvidia
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
