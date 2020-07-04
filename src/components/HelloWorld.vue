<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
  </div>
  <script></script>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Ryoma Hara Portfolio'
    }
  },
  methods: {
    windowResized(){
      resizeCanvas(windowWidth, windowHeight);
      canvasSetup();
    },
    setup(){
      //キャンバスを作成
      canvas = createCanvas(document.documentElement.scrollWidth,document.documentElement.scrollHeight);
      canvas.position(0,0);//canvasをページの原点に固定
      canvas.style('z-index','-1');//canvasを後ろに移動する。
      //背景色
      background(255);
      //図形の線無し
      noStroke();
    },
    draw(){
      frameRate(30);
      //オブジェクトの色をランダム（透明度70）
      fill(random(255),random(255),random(255),70);
      //キャンバスの中心に直径100pxの丸を描画
      ellipse(random(width),random(height),random(100));
    },
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
