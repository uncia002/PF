<template>
  <div class="window">
    <div class="appinfo">
      <div class="overview">
        <div class="name">
          <h1>ABOUT</h1>
        </div>
        <div class="text">
          <p>津山工業高等専門学校情報システム系に在学している庭崎伍です。私はクリエイティブなことが好きなフロントエンドエンジニアです。WebアプリケーションやAR、モーショングラフィックスなど多分野にわたって開発経験があり、中でもデザインにとても興味があります。色々な大会にプロジェクトリーダーとして参加した経験があるため、チームワーク、マネジメントに関するノウハウがあります。</p>
          <h3>経歴</h3>
          <p>中学3年生にプログラミングを知り、独学でWebアプリケーション学び始める。高専に入学、システム研究部と呼ばれる部活でいろいろな人と出会いクリエイティブの楽しさに目覚める。ARCoreを知り、ARについて学習を始める。モーショングラフィックスを知り、デザインを本格的に好きになる。デザインについて調べていくうちに、Webフロントエンドの業界に興味をもち、フロントエンドを学習しはじめる。</p>
        </div>
      </div>
      <div style="height:300px;" class="dream">
        <dl>
          <dt>目標</dt>
          <dd>ビジュアルコーダーとして、表現力とWebGLを磨いていき、洋服のデザイナーズブランドみたいに人の感情、雰囲気を最大限に表現させる事の出来るエンジニアになりたい。</dd>
        </dl>
      </div>
      <div class="his">
        <dl>
          <dt>主な参加イベント</dt>
          <dd>HackU 2018 OSAKA</dd>
          <dd>HackU 2019 OSAKA</dd>
          <dd>群馬プログラミングアワード</dd>
          <dd>パソコン甲子園</dd>
          <dt>スキル</dt>
          <dd>Vue.js</dd>
          <dd>Django</dd>
          <dd>Unity</dd>
          <dd>ARcore</dd>
          <dd>Aviutl</dd>
          <dd>Anime.js</dd>
          <dd>Three.js(勉強中)</dd>
          <dd>その他Vue系ライブラリ</dd>
          <dt>言語</dt>
          <dd>javascript</dd>
          <dd>python</dd>
          <dd>C#</dd>
          <dd>mySQL</dd>


        </dl>
      </div>
    </div>
  </div>
</template>

<script>
export default{
  data(){
    return{
    }
  }
}
</script>

<style scoped>
.window{
  width: 100%;
  min-height: 100%;
}
.appinfo{
  width: 90%;
  margin-bottom: 15px;
  font-family: Modernist;
}
.overview{
}
p{
  font-family: serif;
  font-size: 15px;
  font-weight: 900;
}
.dream dl{
  font-family: serif;
  font-size: 30px;
}
.dream dt {
  float: left;
  clear: left;
  margin-right: 0.5em;
  width: 120px;
  font-weight: 900;
  font-size: 40px;
  color:white;
}

.dream dd {
	float:left;
	margin-left:1em;
}
.movie{
  max-width: 500px;
  margin-bottom: 100px;

  margin: 30px 0;
  display:inline-block;
  border:solid 1px black;
}
.movie video{
  object-fit: contain;
  width: 100%;
}
.his{
  font-family: serif;
}
h3{
  font-weight: 900;
}
.his dl{
  font-family: serif;
}
.his dt {
  float: left;
  clear: left;
  margin-right: 0.5em;
  width: 130px;
  font-weight: 900;
  color:darkgray;
}

.his dd {
	float:left;
	margin-left:1em;
  color:#DDD;
}
</style>
