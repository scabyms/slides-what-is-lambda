---
title: what is lambda
background: /bernice-tong-VPTSmbGba7Q-unsplash.jpg
class: 'text-center'
highlighter: shiki
lineNumbers: false
drawings:
  persist: false
fonts:
  sans: 'Zen Kurenaido'
  serif: 'Zen Kurenaido'
  mono: 'Zen Kurenaido'
clicks: 2
---

<div class="flex justify-center items-end mb-4">
  <div class="text-7xl">What is </div>
  <div class="px-3 grid">
    <div class>
      <span class="line-through pr-2 text-amber-600">ラクダ</span>
      <span class="text-orange-300">ラムダ</span>
    </div>
    <div class="text-orange-300 font-bold text-7xl">Lambda</div>
  </div>
</div>

<div class="opacity-70">~ラムダとラクダの違い~</div>

<p class="opacity-50">その謎を解明するため、我々調査隊はアマゾンの奥地へと向かった</p>

<div class="pt-12">
  <random-fall-texts
    v-if="$slidev.nav.currentPage === 1"
    text="🐪"
    :speed="300"
    :max="50" 
    :interval="400"
    class="text-6xl opacity-50" 
  />
  <random-fall-texts
    v-if="$slidev.nav.currentPage === 1"
    text="🐫"
    :speed="300"
    :max="50" 
    :interval="400"
    class="text-6xl opacity-50" 
  />
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10 scale-110">
    アマゾンの奥地へ進む <carbon:arrow-right class="inline"/>
  </span>
  <slide-text
    v-if="$slidev.nav.currentPage === 1 && $slidev.nav.clicks > 0"
    class="text-8xl"
    text="🐪🐫🐪🐫🐪🐫"
    :y="400"
    :x="-800"
    :speed="3"
    :max="1700"
    @finish="$slidev.nav.nextSlide"
  />
</div>

<div class="absolute bottom-3 left-3 opacity-20 text-sm">画像提供：https://unsplash.com/</div>

---
layout: image
image: /mariam-soliman-Ht5XmeuLyDg-unsplash.jpg
clicks: 1
---

# 🐪まえがき🐫

<div class="text-2xl">
  <div class="text-black">
    <div>今回はAWSの<span class="font-bold text-orange-500">ラムダ</span>というサービスについてご紹介します</div>
    <div>ですが、ただ紹介するだけでは面白味が少ないので</div>
    <div>今回は名前の似ている<span class="font-bold text-amber-700">ラクダ</span>と比較していきます</div>
    <div class="mt-6">なお、名前が似ていること以外に<span class="font-bold text-amber-700">ラクダ</span>を使用した理由は一切ございません</div>
  </div>
</div>
<div
  v-if="$slidev.nav.clicks > 0"
  v-motion-slide-left
  class="absolute top-85 right-70 text-white"
>ひでぇ
</div>

---
layout: intro
---

# 自己紹介

<div class="flex">
  <div class="basis-1/4">
    <img src="/profile.png" class="rounded-full px-6 py-6" />
    <div class="py-3 text-4xl text-center font-bold">WinterYukky</div>
    <div class="flex justify-around">
      <a href="https://github.com/WinterYukky" target="_blank" alt="GitHub" class="text-xl icon-btn opacity-50 !border-none !hover:text-white">
        <mdi-github class="text-3xl" />
      </a>
      <a href="https://twitter.com/WinterYukky" target="_blank" alt="Twitter" class="text-xl icon-btn opacity-50 !border-none !hover:text-sky-500">
        <mdi-twitter class="text-3xl text-sky-500" />
      </a>
    </div>
  </div>
  <div class="basis-2/4 pl-10">
    <ul class="text-2xl">
      <li>大阪のスタートアップ所属</li>
      <li>新規事業推進室 室長</li>
      <li>好きなテクノロジー
        <ul class="text-xl">
          <li>静的型付け言語</li>
          <li>Infrastructure as Code</li>
          <li>CI / CD</li>
        </ul>
      </li>
    </ul>
  </div>
  <div class="basis-1/4 pl-10">
    <img src="/aws-certified-cloud-practitioner.png" class="rounded-full px-6" />
    <img src="/aws-certified-solutions-architect-associate.png" class="rounded-full px-6 pt-6" />
  </div>
</div>

---
layout: image-right
image: /mads-severinsen-g3Auz-nRbjM-unsplash.jpg
clicks: 4
---

<h1><span class="font-bold text-orange-400">AWS Lambda</span>とは</h1>

<ul>
  <li :class="{'opacity-20': $slidev.nav.clicks !== 0}">
    AWSの提供するFaaS
    <li>コード1つでバックエンドが作成可能</li>
    <li>インフラの管理が一切不要</li>
  </li>
  <li :class="{'opacity-20': $slidev.nav.clicks !== 1}">イベントをトリガーに任意のコードを実行</li>
  <li :class="{'opacity-20': $slidev.nav.clicks !== 2}">
    トリガーできるイベントの例
    <li>HTTPリクエストが来た</li>
    <li>ファイルがアップロードされた</li>
    <li>DBへデータが書き込まれた</li>
    <li>etc...</li>
  </li>
  <li :class="{'opacity-20': $slidev.nav.clicks !== 3}">
    ネイティブで使用可能な言語
    <li>Node.js, Python, Go, Java, Ruby, C#, PS</li>
  </li>
  <li :class="{'opacity-20': $slidev.nav.clicks !== 4}">
    Runtime APIを使うと
    <li>Rust, C++, Deno... なんでもOK！</li>
  </li>
</ul>


<onomatopoeia text="もしゃ" :max="3" :x="710" :y="350" />

---
layout: image-left
image: /jonatas-tinoco-o_AoBUaCXPQ-unsplash.jpg
---

# こんなユースケース

<li class="text-xl mt-15">バッチサーバーを置き換える</li>
<div class="mt-1 ml-12 text-md opacity-80">⇒ 頻度によっては費用をほぼゼロに</div>

<li class="text-xl mt-5">DB更新時の通知機能</li>
<div class="mt-1 ml-12 text-md opacity-80">⇒ リアルタイムな通知が可能に</div>

<li class="text-xl mt-5">REST APIのバックエンド</li>
<div class="mt-1 ml-12 text-md opacity-80">⇒ アプリケーションに集中できる</div>

---
layout: image-right
image: /waad-salman3-ONLD6EpW5Vs-unsplash.jpg
clicks: 2
---

<h1><span class="font-bold text-amber-700">ラクダ</span>とは</h1>

<ul>
  <li :class="{'opacity-20': $slidev.nav.clicks !== 0}">
    哺乳綱偶蹄目ラクダ科ラクダ属
    <li>ヒトコブラクダ</li>
    <li>フタコブラクダ</li>
  </li>
  <li :class="{'opacity-20': $slidev.nav.clicks !== 1}">
    ヒトコブラクダ
    <li>野生種は絶滅</li>
    <li>家畜化したもののみ現存</li>
  </li>
  <li :class="{'opacity-20': $slidev.nav.clicks !== 2}">
    フタコブラクダ
    <li>若干の野生種が残存</li>
    <li>絶滅危惧種</li>
  </li>
</ul>

<!-- 哺乳(ほにゅう)綱偶蹄(ぐうてい)目ラクダ科ラクダ属 -->

---

# Lambdaとラクダの比較

両者を比較してみましょう。

<table class="table-auto">
  <thead>
    <tr>
      <th>項目</th>
      <th>Lambda</th>
      <th>🐫ラクダ🐪</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>イベント駆動</td>
      <td>⭕</td>
      <td>❌</td>
    </tr>
    <tr>
      <td>導入初期コスト</td>
      <td>0円</td>
      <td>500万円</td>
    </tr>
    <tr>
      <td>インフラ管理</td>
      <td>不要</td>
      <td>必要</td>
    </tr>
    <tr>
      <td>実行制限時間</td>
      <td>15分</td>
      <td>40年</td>
    </tr>
    <tr>
      <td>利用可能地域</td>
      <td>ほぼ全リージョン</td>
      <td>限定的</td>
    </tr>
  </tbody>
</table>

<div class="pt-12 text-3xl">圧倒的Lambda！！みんなもLambda使っていこう！</div>

---
layout: statement
---

# ご清聴ありがとうございました

<controllable-random-fall-texts v-if="$slidev.nav.currentPage === 8" />

