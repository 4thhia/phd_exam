---
theme: neat
layout: cover
colorSchema: light
coverLogo: figures/utokyo.png
coverTitle: "微分方程式系における強化学習(修士課程の研究)+博士課程での研究計画"
coverAuthor: Haruki Settai
lineNumbers: true
---

<div style="font-size: 0.9em; position: absolute; bottom: -10%; left: 0%; width: 90%; line-height: 1.2;">
  Supervised by Takehisa Yairi, Naoya Takeishi
</div>

---
maxDepth: 2
---

<div style="font-size: 1.2em;">
  <Toc depth="2" />
</div>

---
layout: section
subject: Overview
---

# Overview

---
layout: default
headerEnable: true
headerTitle: Overview
headerLogo: figures/utokyo.png
---

## 本研究の貢献
ダイナミクスが確率微分方程式(SDE)に従う系においてモデルフリーで系の連続性を学習に組み込む強化学習(RL)を提案した。

<div v-click.hide>
<v-clicks>
<div>
<strong>強化学習 (RL)</strong><br>
- <strong class="accent">機械学習の一種で, 最適な行動戦略を学習する。</strong>ロボットの制御, LLMのチューニングなどで使われる。<br>
- 基本的には<strong class="accent">離散的な状態遷移</strong>を行う系上での最適化問題として定式化される。<br>

<figure style="position: absolute; top: 59%; right: 60%; width: 250px; text-align: center;">
  <img src="./figures/rl.gif" style="width: 100%;">
  <figcaption style="font-size: 1.2em; word-wrap: break-word; margin-top: 4px;">
    強化学習の学習プロセス
  </figcaption>
</figure>
</div>

<div>
<strong>確率微分方程式 (SDE)</strong><br>
- 時間発展にノイズが乗った微分方程式

<figure style="position: absolute; top: 59%; right: 20%; width: 300px; text-align: center;">
  <img src="./figures/sde.png" style="width: 100%;">
  <figcaption style="font-size: 1.2em; word-wrap: break-word; margin-top: -6px;">
    SDEのサンプルパス
  </figcaption>
</figure>
</div>

</v-clicks>
</div>

<div v-after>
<strong>強化学習 (RL)</strong><br>
- <strong class="accent">機械学習の一種で, 最適な行動戦略を学習する。</strong>ロボットの制御, LLMのチューニングなどで使われる。<br>
- 基本的には<strong class="accent">離散的な状態遷移</strong>を行う系上での最適化問題として定式化される。<br>
<strong>確率微分方程式 (SDE)</strong><br>
- 時間発展にノイズが乗った微分方程式

  <div style="border: 2px solid #000; padding: 10px; margin: 15px auto; background-color:rgb(243, 255, 243);">
  <strong>本研究の位置づけ</strong><br>
  確率最適制御と強化学習を結ぶ研究。確率最適制御の目標であるHJB方程式を, 強化学習と同様にモデル未知でデータドリブンで解く手法を提案した。
  </div>
</div>

<v-click>
<div style="border: 2px solid #000; padding: 10px; margin: 10px auto; background-color: rgb(255, 235, 240);">
<strong>先行研究からの差分</strong><br>
先行研究では学習のためにモデルを必要としていたため振り子のような簡単な系での実験にとどまっていたが, 本研究では初めてモデルフリーの手法を提案し強化学習の一般的なベンチマークで性能を確かめた。
</div>
</v-click>


<style>
.slidev-vclick-hidden {
  display: none;
}
</style>


---
layout: two-cols
headerEnable: true
headerTitle: Overview
headerLogo: figures/utokyo.png
---

## Motivation

::left::
**強化学習の枠組み**


<div v-click.hide>
  <div v-click.hide>
    <div v-click.hide>
      <div v-click.hide>
        <div v-click.hide>
          <v-click>
            <figure style="position: absolute; top: 30%; left: 8%; width: 350px; text-align: center;">
              <img src="./figures/mdp1.png" style="width: 100%;">
              <figcaption style="font-size: 0.8em; text-align: center; width: 200px; position: absolute; top: 102%; left: 20%;">
              Markov Decision Process (MDP)
              </figcaption>
            </figure>
          </v-click>
        </div>
        <div v-after>
          <figure style="position: absolute; top: 30%; left: 8%; width: 350px; text-align: center;">
            <img src="./figures/mdp2.png" style="width: 100%;">
            <figcaption style="font-size: 0.8em; text-align: center; width: 200px; position: absolute; top: 102%; left: 20%;">
            Markov Decision Process (MDP)
            </figcaption>
          </figure>
        </div>
      </div>
      <div v-after>
        <figure style="position: absolute; top: 30%; left: 8%; width: 350px; text-align: center;">
            <img src="./figures/mdp3.png" style="width: 100%;">
            <figcaption style="font-size: 0.8em; text-align: center; width: 200px; position: absolute; top: 102%; left: 20%;">
            Markov Decision Process (MDP)
            </figcaption>
        </figure>
      </div>
    </div>
    <div v-after>
        <figure style="position: absolute; top: 30%; left: 8%; width: 350px; text-align: center;">
        <img src="./figures/mdp4_5.png" style="width: 100%;">
        <figcaption style="font-size: 0.8em; text-align: center; width: 200px; position: absolute; top: 102%; left: 20%;">
        Markov Decision Process (MDP)
        </figcaption>
        </figure>
    </div>
  </div>
  <div v-after>
    <figure style="position: absolute; top: 30%; left: 8%; width: 350px; text-align: center;">
      <img src="./figures/mdp6.png" style="width: 100%;">
      <figcaption style="font-size: 0.8em; text-align: center; width: 200px; position: absolute; top: 102%; left: 20%;">
      Markov Decision Process (MDP)
      </figcaption>
    </figure>
  </div>
</div>
<div v-after>
  <figure style="position: absolute; top: 30%; left: 8%; width: 350px; text-align: center;">
      <img src="./figures/mdp7_10.png" style="width: 100%;">
      <figcaption style="font-size: 0.8em; text-align: center; width: 200px; position: absolute; top: 102%; left: 20%;">
      Markov Decision Process (MDP)
      </figcaption>
  </figure>
</div>

<v-click>
<figure style="position: absolute; top: 25%; left: 5%; width: 150px; text-align: center;">
  <img src="./figures/othello.png" style="width: 100%;">
</figure>
</v-click>

<v-click>
<figure style="position: absolute; top: 76%; left: 12%; width: 200px; text-align: center;">
  <img src="./figures/rep_mat.png" style="width: 100%;; margin-bottom: 0.5em;">
  <figcaption style="font-size: 0.8em; white-space: nowrap;">
    <strong>Model: Transition Probability Matrix</strong>
  </figcaption>
</figure>
</v-click>

::right::

**Real-World Dynamics**

<v-click>
<figure style="position: absolute; top: 25%; left: 55%; width: 90px; text-align: center;">
  <img src="./figures/rl.gif" style="width: 100%;">
</figure>
</v-click>

<v-click>
<figure style="position: absolute; top: 40%; left: 62.5%; width: 220px; text-align: center;">
  <img src="./figures/continuous.png" style="width: 100%;">
  <figcaption style="font-size: 0.8em; text-align: center; width: 200px; position: absolute; top: 102%; left: 10%;">
    Controlled Diffusion Process
    </figcaption>
</figure>
</v-click>

<v-click>
<figure style="position: absolute; top: 77%; left: 62%; width: 250px; text-align: center;">
  <img src="./figures/sde_eq.png" style="width: 100%; margin-bottom: 0.5em;">
  <figcaption style="font-size: 0.8em; white-space: nowrap;">
    <strong>Model: &mu;, &sigma;</strong>
  </figcaption>
</figure>
</v-click>

<div v-click.hide>
    <v-click>
    <div style="
        position: absolute;
        top: 17%;
        left: 50%;
        width: 410px;
        height: 70%;
        border: 3px solid red;
        border-radius: 0px;
        box-sizing: border-box;
        z-index: 10;
    ">
    </div>
    <div style="
        position: absolute;
        top: 10.5%;
        left: 50%;
        width: 410px;
        font-size: 0.8em;
        font-weight: bold;
        background: white;
        padding: 4px 8px;
        border-radius: 0px;
        border: 3px solid red;
        color: red;
        box-sizing: border-box;
        text-align: center;
    ">
    Can we formulate RL within the framework of this system?
    </div>
    </v-click>
</div>
<div v-after>
  <figure style="position: absolute; top: 48%; left: 46%; width: 80px; text-align: center;">
    <img src="./figures/supset.png" style="width: 100%;">
  </figure>
</div>


<v-click>
<Arrow :x1="600" :y1="435" :x2="369" :y2="471.75" :width="3" class="text-red-500" />
  <svg width="800" height="600" style="position: absolute; top: 0; left: 0; pointer-events: none;">
    <text
        x="487.49"
        y="436.70"
        transform="rotate(-9, 487.49, 436.70)"
        text-anchor="middle"
        dominant-baseline="central"
        font-size="4"
        fill="red"
    >
        変換できる*
    </text>
  </svg>
  <div style="font-size: 0.8em; position: absolute; top: 15%; left: 73%; width: 26%; line-height: 1.2;">
    <span style="color:red">*</span>In continuous time, the object being transformed is the infinitesimal generator, not the transition probability matrix.  The RL framework still applies in the same way.
  </div>
</v-click>


<v-clicks>
  <div style="font-size: 0.9em; position: absolute; bottom: 9%; left: 55%; width: 90%; line-height: 1.2;">
    &rArr; 従来の強化学習をそのまま適用できる。
  </div>
  <div style="font-size: 0.9em; position: absolute; bottom: 1.5%; left: 55%; width: 45%; line-height: 1.2;">
    &rArr; 離散でも連続でも共通で使えるということは, 連続の<br>系に特有の情報を活用できていない。
  </div>
</v-clicks>


---
layout: default
headerEnable: true
headerTitle: Overview
headerLogo: figures/utokyo.png
---

## 研究概要

<script setup>
import AnimatedArrow from './layouts/AnimatedArrow.vue'
</script>

<div v-click.hide>
  <div v-click.hide>
  <figure style="position: absolute; top: 18%; left: 5%; width: 300px; text-align: center;">
    <img src="./figures/RL_methods.png" style="width: 100%;">
    <figcaption style="font-size: 0.8em; text-align: center; width: 200px; position: absolute; top: 102%; left: 15%;">
      RL Algorithms
    </figcaption>
  </figure>
  </div>

  <div v-after>
    <figure style="position: absolute; top: 74.0%; left: 37%; width: 70px; text-align: center; z-index: 1;">
      <img src="./figures/unexploited_continuity.png" style="width: 100%;">
    </figure>
    <div>
      <AnimatedArrow
        id="arrow1"
        :points="[
          [300, 520],
          [300, 530],
          [222, 530]
        ]"
        :stroke-width="4"
        color="#589EFB"
        :glass="true"
      />
    </div>
    <figure style="position: absolute; top: 18%; left: 5%; width: 300px; text-align: center;">
      <img src="./figures/RL_methods_dtd.png" style="width: 100%;">
      <figcaption style="font-size: 0.8em; text-align: center; width: 200px; position: absolute; top: 102%; left: 15%;">
        RL Algorithms
      </figcaption>
    </figure>
    <div style="font-size: 0.9em; position: absolute; top: 67%; left: 46%; width: 45%; line-height: 1.2;">
    <strong>1. 提案手法</strong><br>
      状態発展のモデルを用いずに, 状態発展の連続性を組み込んで学習できるTD法を提案した。<div style="height: 0.3em;"></div>
    <strong>2. 解析</strong><br>
      状態発展が滑らかであるほど収束が速いことを示した。
    </div>
  </div>
</div>
<div v-after>
  <figure style="position: absolute; top: 74.0%; left: 37%; width: 70px; text-align: center; z-index: 1;">
    <img src="./figures/unexploited_continuity.png" style="width: 100%;">
  </figure>
  <div>
    <AnimatedArrow
      id="arrow1"
      :points="[
        [300, 520],
        [300, 530],
        [222, 530]
      ]"
      :stroke-width="4"
      color="#589EFB"
      :glass="true"
    />
  </div>
  <figure style="position: absolute; top: 18%; left: 5%; width: 300px; text-align: center;">
    <img src="./figures/RL_methods_dtd2.png" style="width: 100%;">
    <figcaption style="font-size: 0.8em; text-align: center; width: 200px; position: absolute; top: 102%; left: 15%;">
      RL Algorithms
    </figcaption>
  </figure>
  <div style="font-size: 0.9em; position: absolute; top: 67%; left: 46%; width: 45%; line-height: 1.2;">
  <strong>1. 提案手法</strong><br>
    状態発展のモデルを用いずに, 状態発展の連続性を組み込んで学習できるTD法(differential TD: dTD)を提案した。<div style="height: 0.3em;"></div>
  <strong>2. 解析</strong><br>
    状態発展が滑らかであるほど収束が速いことを示した。
  </div>
  <div>
    <AnimatedArrow
      id="arrow2"
      :points="[
        [176, 520],
        [176, 476.8],
        [104.5, 476.8],
        [104.5, 457],
      ]"
      :stroke-width="4"
      color="#589EFB"
      :glass="true"
    />
  </div>
  <div>
    <AnimatedArrow
      id="arrow3"
      :points="[
        [104.5, 420],
        [104.5, 406],
        [147, 406],
        [147, 208]
      ]"
      :stroke-width="4"
      color="#589EFB"
      :glass="true"
    />
  </div>
  <div style="font-size: 0.9em; position: absolute; top: 25%; left: 31%; width: 45%; line-height: 1.2;">
  <strong>3. 実験</strong><br>
    連続系のベンチマークであるMujocoを用いて, 従来のTDに基づいたPPOと, 提案手法であるdTDに基づいたPPOを比較した。提案手法が学習効率を改善することを実験的に示した。<br>
  </div>

  <figure style="position: absolute; top: 42%; left: 40%; width: 300px; text-align: center;">
    <img src="./figures/brax.gif" style="width: 100%;">
    <figcaption style="font-size: 0.8em; white-space: nowrap;">
    brax simulator
    </figcaption>
  </figure>
</div>

---
layout: section
subject: Preliminaries on RL
---

# Preliminaries on RL

---
layout: two-cols
headerEnable: true
headerTitle: Preliminaries on RL
headerLogo: figures/utokyo.png
---

**TD method**

::left::

**Discrete**

<div v-click.hide>
  <figure style="position: absolute; top: 15%; right: 5%; width: 300px; text-align: center;">
    <img src="./figures/RL_methods_td.png" style="width: 100%;">
  </figure>
  <div v-click.hide>
    <div v-click.hide>
      <div v-click.hide>
        <div v-click.hide>
          <div v-click.hide>
            <div v-click.hide>
              <div v-click.hide>
                <div v-click.hide>
                  <div v-click.hide>
                    <div v-click.hide>
                      <div v-click.hide>
                        <div v-click.hide>
                          <div v-click.hide>
                            <div v-click.hide>
                              <v-click>
                                <figure style="position: relative; top: 0%; left: 0%; width: 220px; text-align: center;">
                                    <img src="./figures/mdp1.png" style="width: 100%;">
                                    <figcaption style="font-size: 0.8em; text-align: center; width: 200px; position: absolute; top: 102%; left: 0%;">
                                    MDP
                                    </figcaption>
                                </figure>
                              </v-click>
                            </div>
                            <div v-after>
                              <figure style="position: relative; top: 0%; left: 0%; width: 220px; text-align: center;">
                                <img src="./figures/mdp2.png" style="width: 100%;">
                                <figcaption style="font-size: 0.8em; text-align: center; width: 200px; position: absolute; top: 102%; left: 0%;">
                                MDP
                                </figcaption>
                              </figure>
                            </div>
                          </div>
                          <div v-after>
                            <figure style="position: relative; top: 0%; left: 0%; width: 220px; text-align: center;">
                              <img src="./figures/mdp3.png" style="width: 100%;">
                              <figcaption style="font-size: 0.8em; text-align: center; width: 200px; position: absolute; top: 102%; left: 0%;">
                              MDP
                              </figcaption>
                            </figure>
                          </div>
                        </div>
                        <div v-after>
                          <figure style="position: relative; top: 0%; left: 0%; width: 220px; text-align: center;">
                            <img src="./figures/mdp4_5.png" style="width: 100%;">
                            <figcaption style="font-size: 0.8em; text-align: center; width: 200px; position: absolute; top: 102%; left: 0%;">
                            MDP
                            </figcaption>
                          </figure>
                        </div>
                      </div>
                      <div v-after>
                        <figure style="position: relative; top: 0%; left: 0%; width: 220px; text-align: center;">
                          <img src="./figures/mdp6.png" style="width: 100%;">
                          <figcaption style="font-size: 0.8em; text-align: center; width: 200px; position: absolute; top: 102%; left: 0%;">
                          MDP
                          </figcaption>
                        </figure>
                      </div>
                    </div>
                    <div v-after>
                      <figure style="position: relative; top: 0%; left: 0%; width: 220px; text-align: center;">
                        <img src="./figures/mdp7_10.png" style="width: 100%;">
                        <figcaption style="font-size: 0.8em; text-align: center; width: 200px; position: absolute; top: 102%; left: 0%;">
                        MDP
                        </figcaption>
                      </figure>
                    </div>
                  </div>
                  <div v-after>
                    <figure style="position: relative; top: 0%; left: 0%; width: 220px; text-align: center;">
                      <img src="./figures/mdp7_10.png" style="width: 100%;">
                      <figcaption style="font-size: 0.8em; text-align: center; width: 200px; position: absolute; top: 102%; left: 0%;">
                      MDP
                      </figcaption>
                    </figure>
                    <figure style="position: absolute; top: 39.4%; left: 26%; width: 150px; text-align: center;">
                      <img src="./figures/rep_mat.png" style="width: 100%;">
                      <figcaption style="font-size: 0.8em; text-align: center; width: 200px; position: absolute; top: 120%; left: -15%;">
                      Model
                      </figcaption>
                    </figure>
                  </div>
                </div>
                <div v-after>
                  <figure style="position: relative; top: 0%; left: 0%; width: 220px; text-align: center;">
                    <img src="./figures/mdp_value.png" style="width: 100%;">
                    <figcaption style="font-size: 0.8em; text-align: center; width: 200px; position: absolute; top: 102%; left: 0%;">
                    MDP
                    </figcaption>
                  </figure>
                  <figure style="position: absolute; top: 39.4%; left: 26%; width: 150px; text-align: center;">
                    <img src="./figures/rep_mat.png" style="width: 100%;">
                    <figcaption style="font-size: 0.8em; text-align: center; width: 200px; position: absolute; top: 120%; left: -15%;">
                    Model
                    </figcaption>
                  </figure>
                  <figure style="position: absolute; top: 61%; left: 14%; width: 80px; text-align: center;">
                    <img src="./figures/value_fn.png" style="width: 100%;">
                    <figcaption style="font-size: 1.2em; position: absolute; top: -25%; left: -125%; font-size: 0.8em; white-space: nowrap;">
                    <strong>Value function:</strong>
                    </figcaption>
                  </figure>
                  <div style="font-size: 0.9em; position: absolute; top: 60.3%; left: 22%; width: 250px; text-align: center;">
                    ←この関数(価値関数)を知りたい
                  </div>
                </div>
              </div>
              <div v-after>
                <figure style="position: relative; top: 0%; left: 0%; width: 220px; text-align: center;">
                  <img src="./figures/mdp_value2.png" style="width: 100%;">
                  <figcaption style="font-size: 0.8em; text-align: center; width: 200px; position: absolute; top: 102%; left: 0%;">
                  MDP
                  </figcaption>
                </figure>
                <figure style="position: absolute; top: 39.4%; left: 26%; width: 150px; text-align: center;">
                  <img src="./figures/rep_mat.png" style="width: 100%;">
                  <figcaption style="font-size: 0.8em; text-align: center; width: 200px; position: absolute; top: 120%; left: -15%;">
                  Model
                  </figcaption>
                </figure>
                <figure style="position: absolute; top: 61%; left: 14%; width: 80px; text-align: center;">
                  <img src="./figures/value_fn.png" style="width: 100%;">
                  <figcaption style="font-size: 1.2em; position: absolute; top: -25%; left: -125%; font-size: 0.8em; white-space: nowrap;">
                  <strong>Value function:</strong>
                  </figcaption>
                </figure>
                <div style="font-size: 0.9em; position: absolute; top: 60.3%; left: 22%; width: 250px; text-align: center;">
                  ←この関数(価値関数)を知りたい
                </div>
              </div>
            </div>
            <div v-after>
              <figure style="position: relative; top: 0%; left: 0%; width: 220px; text-align: center;">
                <img src="./figures/mdp_value3.png" style="width: 100%;">
                <figcaption style="font-size: 0.8em; text-align: center; width: 200px; position: absolute; top: 102%; left: 0%;">
                MDP
                </figcaption>
              </figure>
              <figure style="position: absolute; top: 39.4%; left: 26%; width: 150px; text-align: center;">
                <img src="./figures/rep_mat.png" style="width: 100%;">
                <figcaption style="font-size: 0.8em; text-align: center; width: 200px; position: absolute; top: 120%; left: -15%;">
                Model
                </figcaption>
              </figure>
              <figure style="position: absolute; top: 61%; left: 14%; width: 80px; text-align: center;">
                <img src="./figures/value_fn.png" style="width: 100%;">
                <figcaption style="font-size: 1.2em; position: absolute; top: -25%; left: -125%; font-size: 0.8em; white-space: nowrap;">
                <strong>Value function:</strong>
                </figcaption>
              </figure>
              <div style="font-size: 0.9em; position: absolute; top: 60.3%; left: 22%; width: 250px; text-align: center;">
                ←この関数(価値関数)を知りたい
              </div>
            </div>
          </div>
          <div v-after>
            <figure style="position: relative; top: 0%; left: 0%; width: 220px; text-align: center;">
              <img src="./figures/mdp_value4.png" style="width: 100%;">
              <figcaption style="font-size: 0.8em; text-align: center; width: 200px; position: absolute; top: 102%; left: 0%;">
              MDP
              </figcaption>
            </figure>
            <figure style="position: absolute; top: 39.4%; left: 26%; width: 150px; text-align: center;">
              <img src="./figures/rep_mat.png" style="width: 100%;">
              <figcaption style="font-size: 0.8em; text-align: center; width: 200px; position: absolute; top: 120%; left: -15%;">
              Model
              </figcaption>
            </figure>
            <figure style="position: absolute; top: 61%; left: 14%; width: 80px; text-align: center;">
              <img src="./figures/value_fn.png" style="width: 100%;">
              <figcaption style="font-size: 1.2em; position: absolute; top: -25%; left: -125%; font-size: 0.8em; white-space: nowrap;">
              <strong>Value function:</strong>
              </figcaption>
            </figure>
            <div style="font-size: 0.9em; position: absolute; top: 60.3%; left: 22%; width: 250px; text-align: center;">
              ←この関数(価値関数)を知りたい
            </div>
          </div>
        </div>
        <div v-after>
          <figure style="position: relative; top: 0%; left: 0%; width: 220px; text-align: center;">
            <img src="./figures/mdp_value5.png" style="width: 100%;">
            <figcaption style="font-size: 0.8em; text-align: center; width: 200px; position: absolute; top: 102%; left: 0%;">
            MDP
            </figcaption>
          </figure>
          <figure style="position: absolute; top: 39.4%; left: 26%; width: 150px; text-align: center;">
            <img src="./figures/rep_mat.png" style="width: 100%;">
            <figcaption style="font-size: 0.8em; text-align: center; width: 200px; position: absolute; top: 120%; left: -15%;">
            Model
            </figcaption>
          </figure>
          <figure style="position: absolute; top: 61%; left: 14%; width: 80px; text-align: center;">
            <img src="./figures/value_fn.png" style="width: 100%;">
            <figcaption style="font-size: 1.2em; position: absolute; top: -25%; left: -125%; font-size: 0.8em; white-space: nowrap;">
            <strong>Value function:</strong>
            </figcaption>
          </figure>
          <div style="font-size: 0.9em; position: absolute; top: 60.3%; left: 22%; width: 250px; text-align: center;">
            ←この関数(価値関数)を知りたい
          </div>
        </div>
      </div>
      <div v-after>
        <figure style="position: relative; top: 0%; left: 0%; width: 220px; text-align: center;">
          <img src="./figures/mdp_value5.png" style="width: 100%;">
          <figcaption style="font-size: 0.8em; text-align: center; width: 200px; position: absolute; top: 102%; left: 0%;">
          MDP
          </figcaption>
        </figure>
        <figure style="position: absolute; top: 39.4%; left: 26%; width: 150px; text-align: center;">
          <img src="./figures/rep_mat.png" style="width: 100%;">
          <figcaption style="font-size: 0.8em; text-align: center; width: 200px; position: absolute; top: 120%; left: -15%;">
          Model
          </figcaption>
        </figure>
        <figure style="position: absolute; top: 61%; left: 14%; width: 80px; text-align: center;">
          <img src="./figures/value_fn.png" style="width: 100%;">
          <figcaption style="font-size: 1.2em; position: absolute; top: -25%; left: -125%; font-size: 0.8em; white-space: nowrap;">
          <strong>Value function:</strong>
          </figcaption>
        </figure>
        <div style="font-size: 0.9em; position: absolute; top: 60.3%; left: 22%; width: 250px; text-align: center;">
          ←この関数(価値関数)を知りたい
        </div>
        <figure style="position: absolute; top: 67%; left: 15.6%; width: 260px; text-align: center;">
          <img src="./figures/bellman.png" style="width: 100%;">
          <figcaption style="font-size: 1.2em; position: absolute; top: -10%; left: -45%; font-size: 0.8em; white-space: nowrap;">
          <strong>Bellman equation:</strong>
          </figcaption>
        </figure>
        <div style="font-size: 0.9em; position: absolute; top: 66.3%; left: 39%; width: 400px; text-align: center;">
          ←価値関数が満たすべき方程式(ベルマン方程式)
        </div>
      </div>
    </div>
    <div v-after>
      <figure style="position: relative; top: 0%; left: 0%; width: 220px; text-align: center;">
        <img src="./figures/mdp_value5_nn.png" style="width: 100%;">
        <figcaption style="font-size: 0.8em; text-align: center; width: 200px; position: absolute; top: 102%; left: 0%;">
        MDP
        </figcaption>
      </figure>
      <figure style="position: absolute; top: 39.4%; left: 26%; width: 150px; text-align: center;">
        <img src="./figures/rep_mat.png" style="width: 100%;">
        <figcaption style="font-size: 0.8em; text-align: center; width: 200px; position: absolute; top: 120%; left: -15%;">
        Model
        </figcaption>
      </figure>
      <figure style="position: absolute; top: 61%; left: 14%; width: 80px; text-align: center;">
        <img src="./figures/value_fn.png" style="width: 100%;">
        <figcaption style="font-size: 1.2em; position: absolute; top: -25%; left: -125%; font-size: 0.8em; white-space: nowrap;">
        <strong>Value function:</strong>
        </figcaption>
      </figure>
      <div style="font-size: 0.9em; position: absolute; top: 60.3%; left: 22%; width: 250px; text-align: center;">
        ←この関数(価値関数)を知りたい
      </div>
      <figure style="position: absolute; top: 67%; left: 15.6%; width: 260px; text-align: center;">
        <img src="./figures/bellman.png" style="width: 100%;">
        <figcaption style="font-size: 1.2em; position: absolute; top: -10%; left: -45%; font-size: 0.8em; white-space: nowrap;">
        <strong>Bellman equation:</strong>
        </figcaption>
      </figure>
      <div style="font-size: 0.9em; position: absolute; top: 66.3%; left: 39%; width: 400px; text-align: center;">
        ←価値関数が満たすべき方程式(ベルマン方程式)
      </div>
      <figure style="position: absolute; top: 72.5%; left: 13.8%; width: 320px; text-align: center;">
        <img src="./figures/true_loss.png" style="width: 100%;">
        <figcaption style="font-size: 1.2em; position: absolute; top: 18%; left: -32%; font-size: 0.8em; white-space: nowrap;">
        <strong>(True) TD Loss:</strong>
        </figcaption>
      </figure>
      <div style="font-size: 0.9em; position: absolute; top: 73.3%; left: 37%; width: 370px; text-align: center;">
        ←Deep RLの真の目的関数
      </div>
    </div>
    <v-click>
      <figure style="position: absolute; top: 74.1%; left: 20.5%;">
        <img src="./figures/circ.png" style="width: 60%;">
      </figure>
      <div style="font-size: 0.9em; position: absolute; top: 77%; left: 35.8%; width: 400px; text-align: center;">
        (モデル未知なので計算不可)
      </div>
    </v-click>
  </div>
  <div v-after>
    <figure style="position: relative; top: 0%; left: 0%; width: 220px; text-align: center;">
      <img src="./figures/mdp_value6.png" style="width: 100%;">
      <figcaption style="font-size: 0.8em; text-align: center; width: 200px; position: absolute; top: 102%; left: 0%;">
      MDP
      </figcaption>
    </figure>
    <figure style="position: absolute; top: 39.4%; left: 26%; width: 150px; text-align: center;">
      <img src="./figures/rep_mat.png" style="width: 100%;">
      <figcaption style="font-size: 0.8em; text-align: center; width: 200px; position: absolute; top: 120%; left: -15%;">
      Model
      </figcaption>
    </figure>
    <figure style="position: absolute; top: 61%; left: 14%; width: 80px; text-align: center;">
      <img src="./figures/value_fn.png" style="width: 100%;">
      <figcaption style="font-size: 1.2em; position: absolute; top: -25%; left: -125%; font-size: 0.8em; white-space: nowrap;">
      <strong>Value function:</strong>
      </figcaption>
    </figure>
    <div style="font-size: 0.9em; position: absolute; top: 60.3%; left: 22%; width: 250px; text-align: center;">
      ←この関数(価値関数)を知りたい
    </div>
    <figure style="position: absolute; top: 67%; left: 15.6%; width: 260px; text-align: center;">
      <img src="./figures/bellman.png" style="width: 100%;">
      <figcaption style="font-size: 1.2em; position: absolute; top: -10%; left: -45%; font-size: 0.8em; white-space: nowrap;">
      <strong>Bellman equation:</strong>
      </figcaption>
    </figure>
    <div style="font-size: 0.9em; position: absolute; top: 66.3%; left: 39%; width: 400px; text-align: center;">
      ←価値関数が満たすべき方程式(ベルマン方程式)
    </div>
    <figure style="position: absolute; top: 72.5%; left: 13.8%; width: 320px; text-align: center;">
      <img src="./figures/true_loss.png" style="width: 100%;">
      <figcaption style="font-size: 1.2em; position: absolute; top: 18%; left: -32%; font-size: 0.8em; white-space: nowrap;">
      <strong>(True) TD Loss:</strong>
      </figcaption>
    </figure>
    <div style="font-size: 0.9em; position: absolute; top: 73.3%; left: 37%; width: 370px; text-align: center;">
      ←Deep RLの真の目的関数
    </div>
    <figure style="position: absolute; top: 74.1%; left: 20.5%;">
      <img src="./figures/circ.png" style="width: 60%;">
    </figure>
    <div style="font-size: 0.9em; position: absolute; top: 77%; left: 35.8%; width: 400px; text-align: center;">
      (モデル未知なので計算不可)
    </div>
    <figure style="position: absolute; top: 80.0%; left: 10%; width: 270px; text-align: center;">
      <img src="./figures/loss.png" style="width: 100%;">
      <figcaption style="font-size: 1.2em; position: absolute; top: 17%; left: -23%; font-size: 0.8em; white-space: nowrap;">
      <strong>TD Loss:</strong>
      </figcaption>
    </figure>
    <div style="font-size: 0.9em; position: absolute; top: 81.0%; left: 28%; width: 400px; text-align: center;">
      ←Deep RLの目的関数
    </div>
  </div>
</div>

<div v-after>
  <figure style="position: relative; top: 0%; left: 0%; width: 220px; text-align: center;">
    <img src="./figures/mdp_value6.png" style="width: 100%;">
    <figcaption style="font-size: 0.8em; text-align: center; width: 200px; position: absolute; top: 102%; left: 0%;">
    MDP
    </figcaption>
  </figure>
  <figure style="position: absolute; top: 39.4%; left: 26%; width: 150px; text-align: center;">
    <img src="./figures/rep_mat.png" style="width: 100%;">
    <figcaption style="font-size: 0.8em; text-align: center; width: 200px; position: absolute; top: 120%; left: -15%;">
    Model
    </figcaption>
  </figure>

  <figure style="position: absolute; top: 61%; left: 14%; width: 80px; text-align: center;">
    <img src="./figures/value_fn.png" style="width: 100%;">
    <figcaption style="font-size: 1.2em; position: absolute; top: -25%; left: -125%; font-size: 0.8em; white-space: nowrap;">
    <strong>Value function:</strong>
    </figcaption>
  </figure>

  <figure style="position: absolute; top: 67%; left: 15.6%; width: 260px; text-align: center;">
    <img src="./figures/bellman.png" style="width: 100%;">
    <figcaption style="font-size: 1.2em; position: absolute; top: -10%; left: -45%; font-size: 0.8em; white-space: nowrap;">
    <strong>Bellman equation:</strong>
    </figcaption>
  </figure>

  <figure style="position: absolute; top: 72.5%; left: 13.8%; width: 320px; text-align: center;">
    <img src="./figures/true_loss.png" style="width: 100%;">
    <figcaption style="font-size: 1.2em; position: absolute; top: 18%; left: -32%; font-size: 0.8em; white-space: nowrap;">
    <strong>(True) TD Loss:</strong>
    </figcaption>
  </figure>

  <figure style="position: absolute; top: 80.0%; left: 10%; width: 270px; text-align: center;">
    <img src="./figures/loss.png" style="width: 100%;">
    <figcaption style="font-size: 1.2em; position: absolute; top: 17%; left: -23%; font-size: 0.8em; white-space: nowrap;">
    <strong>TD Loss:</strong>
    </figcaption>
  </figure>
</div>


::right::

**Continuous**

<v-click>
<figure style="position: relative; top: 0%; left: 3%; width: 185px; text-align: center;">
  <img src="./figures/continuous.png" style="width: 100%;">
  <figcaption style="font-size: 0.8em; text-align: center; width: 200px; position: absolute; top: 102%; left: 0%;">
  Continuous MDP
  </figcaption>
</figure>
<figure style="position: absolute; top: 35%; left: 75%; width: 150px; text-align: center;">
  <img src="./figures/sde_eq.png" style="width: 100%;">
  <figcaption style="font-size: 0.8em; text-align: center; width: 200px; position: absolute; top: 120%; left: -18%;">
  Model
  </figcaption>
</figure>
<figure style="position: absolute; top: 42%; left: 82%; width: 10px; text-align: center;">
  <img src="./figures/downarrow.png" style="width: 100%;">
</figure>
<figure style="position: absolute; top: 48%; left: 78%; width: 90px; text-align: center;">
  <img src="./figures/operator.png" style="width: 100%;">
  <figcaption style="font-size: 0.8em; text-align: center; width: 200px; position: absolute; top: 120%; left: -60%;">
  Model (another expression)
  </figcaption>
</figure>


<figure style="position: absolute; top: 61%; left: 62%; width: 80px; text-align: center;">
  <img src="./figures/value_fn.png" style="width: 100%;">
  <figcaption style="font-size: 1.2em; position: absolute; top: -25%; left: -125%; font-size: 0.8em; white-space: nowrap;">
  <strong>Value function:</strong>
  </figcaption>
</figure>

<figure style="position: absolute; top: 67%; left: 63.8%; width: 295px; text-align: center;">
  <img src="./figures/c_bellman.png" style="width: 100%;">
  <figcaption style="font-size: 1.2em; position: absolute; top: -12%; left: -40%; font-size: 0.8em; white-space: nowrap;">
  <strong>Bellman equation:</strong>
  </figcaption>
</figure>

<figure style="position: absolute; top: 72.5%; left: 61.8%; width: 360px; text-align: center;">
  <img src="./figures/c_true_loss.png" style="width: 100%;">
  <figcaption style="font-size: 1.2em; position: absolute; top: 19%; left: -28%; font-size: 0.8em; white-space: nowrap;">
  <strong>(True) TD Loss:</strong>
  </figcaption>
</figure>

<figure style="position: absolute; top: 80.0%; left: 58%; width: 310px; text-align: center;">
  <img src="./figures/c_loss.png" style="width: 100%;">
  <figcaption style="font-size: 1.2em; position: absolute; top: 17%; left: -20%; font-size: 0.8em; white-space: nowrap;">
  <strong>TD Loss:</strong>
  </figcaption>
</figure>
</v-click>

<v-click>
  <figure style="position: absolute; bottom: 13%; left: 15.5%">
    <img src="./figures/underline1.png" style="width: 52%;">
  </figure>
  <figure style="position: absolute; bottom: 13.5%; left: 63.5%;">
    <img src="./figures/underline2.png" style="width: 70%;">
  </figure>
  <div style="font-size: 0.9em; position: absolute; bottom: 5%; left: 20%; width: 600px; text-align: center;">
     系が連続だとわかっていても更新則にその情報が組み込まれていないため, 強化学習Agentは自分がいる系が離散か連続かわからない。
  </div>
</v-click>

<style>
.slidev-vclick-hidden {
  display: none;
}
</style>

---
layout: section
subject: Our Approach
---

# Our Approach

---
layout: two-cols
headerEnable: true
headerTitle: Our Approach - Method
headerLogo: figures/utokyo.png
---

## Core Idea

::left::

**Discrete**


<figure style="position: relative; top: 0%; left: 0%; width: 220px; text-align: center;">
  <img src="./figures/mdp_value.png" style="width: 100%;">
  <figcaption style="font-size: 0.8em; text-align: center; width: 200px; position: absolute; top: 102%; left: 0%;">
  MDP
  </figcaption>
</figure>
<figure style="position: absolute; top: 39.4%; left: 26%; width: 150px; text-align: center;">
  <img src="./figures/rep_mat.png" style="width: 100%;">
  <figcaption style="font-size: 0.8em; text-align: center; width: 200px; position: absolute; top: 120%; left: -15%;">
  Model
  </figcaption>
</figure>

<figure style="position: absolute; top: 61%; left: 13.8%; width: 320px; text-align: center;">
  <img src="./figures/true_loss.png" style="width: 100%;">
  <figcaption style="font-size: 1.2em; position: absolute; top: 18%; left: -32%; font-size: 0.8em; white-space: nowrap;">
  <strong>(True) TD Loss:</strong>
  </figcaption>
</figure>

<figure style="position: absolute; top: 73%; left: 10%; width: 270px; text-align: center;">
  <img src="./figures/loss.png" style="width: 100%;">
  <figcaption style="font-size: 1.2em; position: absolute; top: 17%; left: -23%; font-size: 0.8em; white-space: nowrap;">
  <strong>TD Loss:</strong>
  </figcaption>
</figure>


<v-click>
  <figure style="position: absolute; top: 54.9%; left: 21.1%;">
    <img src="./figures/discrete_arrow.png" style="width: 60%;">
  </figure>
  <figure style="position: absolute; top: 62.5%; left: 20.5%;">
    <img src="./figures/circ.png" style="width: 60%;">
  </figure>

  <figure style="position: absolute; top: 51.9%; left: 68.9%;">
    <img src="./figures/continuous_arrow1.png" style="width: 55%;">
  </figure>
  <figure style="position: absolute; top: 62.6%; left: 68.3%;">
    <img src="./figures/circ.png" style="width: 60%;">
  </figure>
</v-click>

::right::

**Continuous**


<figure style="position: relative; top: 0%; left: 3%; width: 185px; text-align: center;">
  <img src="./figures/continuous.png" style="width: 100%;">
  <figcaption style="font-size: 0.8em; text-align: center; width: 200px; position: absolute; top: 102%; left: 0%;">
  Continuous MDP
  </figcaption>
</figure>
<figure style="position: absolute; top: 35%; left: 75%; width: 150px; text-align: center;">
  <img src="./figures/sde_eq.png" style="width: 100%;">
  <figcaption style="font-size: 0.8em; text-align: center; width: 200px; position: absolute; top: 120%; left: -18%;">
  Model
  </figcaption>
</figure>
<figure style="position: absolute; top: 43%; left: 82%; width: 10px; text-align: center;">
  <img src="./figures/downarrow.png" style="width: 100%;">
</figure>
<figure style="position: absolute; top: 48%; left: 78%; width: 90px; text-align: center;">
  <img src="./figures/operator.png" style="width: 100%;">
  <figcaption style="font-size: 0.8em; text-align: center; width: 200px; position: absolute; top: 120%; left: -60%;">
  Model (another expression)
  </figcaption>
</figure>


<figure style="position: absolute; top: 61%; left: 61.8%; width: 360px; text-align: center;">
  <img src="./figures/c_true_loss.png" style="width: 100%;">
  <figcaption style="font-size: 1.2em; position: absolute; top: 19%; left: -28%; font-size: 0.8em; white-space: nowrap;">
  <strong>(True) TD Loss:</strong>
  </figcaption>
</figure>

<figure style="position: absolute; top: 73%; left: 58%; width: 310px; text-align: center;">
  <img src="./figures/c_loss.png" style="width: 100%;">
  <figcaption style="font-size: 1.2em; position: absolute; top: 17%; left: -20%; font-size: 0.8em; white-space: nowrap;">
  <strong>TD Loss:</strong>
  </figcaption>
</figure>

<v-click>
  <v-click>
    <figure style="position: absolute; top: 66.4%; left: 68.4%;">
      <img src="./figures/model_blocked.png" style="width: 50%;">
    </figure>
  </v-click>
</v-click>

<v-click>
  <figure style="position: absolute; top: 56%; left: 70%;">
    <img src="./figures/model_arg.png" style="width: 50%;">
  </figure>
</v-click>

<v-click>
  <figure style="position: absolute; top: 65.4%; left: 79.1%;">
    <img src="./figures/model_loss.png" style="width: 50%;">
  </figure>
  <div style="font-size: 0.8em; position: absolute; bottom: 26.5%; left: 63%; width: 500px; text-align: center; color: rgb(63, 22, 255); text-shadow: 0 0 0.5px rgb(63, 22, 255);">
     Embed the model into the <br> sample based loss
  </div>
  <div style="font-size: 0.9em; position: absolute; bottom: 7%; left: 20%; width: 550px; text-align: center; text-shadow: 0 0 0.5px rgb(0, 0, 0);">
     モデルを<span style="color: rgb(252, 18, 14);">期待値の添え字</span> だけでなく<span style="color: rgb(63, 22, 255);">引数</span>にも組み込むことで真の目的関数をサンプル近似した後でもモデルの連続性の情報が残るようにする。
  </div>
</v-click>


<style>
.slidev-vclick-hidden {
  display: none;
}
</style>


---
layout: default
headerEnable: true
headerTitle: Our Approach - Method
headerLogo: figures/utokyo.png
---

## Embedding the model introduces another problem


<div style="font-size: 0.8em; position: absolute; top: 20%; left: 8% ;">
$$
\begin{aligned}
V^\pi(s_t) &= \mathbb{E}_{P_\pi}\left[\rho(s_t, A_t)\Delta t+e^{-\gamma\Delta t}V^\pi(S_{t+\Delta t})\right] \\
\end{aligned}
$$
</div>

<v-click>
  <figure style="position: absolute; top: 27.2%; left: 33.3%">
    <img src="./figures/underline3.png" style="width: 49%;">
  </figure>
  <div style="font-size: 0.9em; position: absolute; top: 28.5%; left: 33.5%; width: 650px;">
      Embed the model here, <br> i.e., expand this term using:
  </div>
  <div style="font-size: 0.8em; position: absolute; top: 30.3%; left: 52.5% ;">
$$
\begin{aligned}
dS_t &= \mu(S_t, A_t)dt+\sigma(S_t, A_t)dB_t \\
\end{aligned}
$$
</div>
</v-click>



<v-click>
<div style="font-size: 0.8em; position: absolute; top: 36%; left: 4.7% ;">
$$
\begin{aligned}
\Longrightarrow V^\pi(s_t) &= \frac{1}{\gamma}\mathbb{E}_{P_\pi}\left[\rho(s_t, A_t)+\sum_{i=1}^{n} \mu^i(s_t, A_t)\frac{\partial V^{\pi}(s)}{\partial s^i} \bigg|_{s_t}+ \frac{1}{2} \sum_{i=1}^{n} \sum_{j=1}^{n}[\sigma(s_t, A_t)\sigma^\top(s_t, A_t)]^{ij}\frac{\partial^2 V^{\pi}(s)}{\partial s^i \partial s^j}\bigg|_{s_t}\right]
\end{aligned}
$$
</div>
</v-click>

<v-click>
<div style="font-size: 0.8em; position: absolute; top: 54%; left: 2% ;">
$$
\begin{aligned}
\text{(True) TD Loss: } \mathcal{L}(\theta) &= \left(\frac{1}{\gamma}\mathbb{E}_{P_\pi}\left[\rho(s_t, A_t)+\sum_{i=1}^{n} \mu^i(s_t, A_t)\frac{\partial \tilde{V}_\theta^{\pi}(s)}{\partial s^i} \bigg|_{s_t}+ \frac{1}{2} \sum_{i=1}^{n} \sum_{j=1}^{n}[\sigma(s_t, A_t)\sigma^\top(s_t, A_t)]^{ij}\frac{\partial^2 \tilde{V}_\theta^{\pi}(s)}{\partial s^i \partial s^j}\bigg|_{s_t}\right] - \tilde{V}_\theta^\pi(s_t)\right)^2, \\
\text{TD Loss: } \tilde{\mathcal{L}}(\theta) &= \left(\frac{1}{\gamma}\left(\rho(s_t, A_t)+\sum_{i=1}^{n} \mu^i(s_t, A_t)\frac{\partial \tilde{V}_\theta^{\pi}(s)}{\partial s^i} \bigg|_{s_t}+ \frac{1}{2} \sum_{i=1}^{n} \sum_{j=1}^{n}[\sigma(s_t, A_t)\sigma^\top(s_t, A_t)]^{ij}\frac{\partial^2 \tilde{V}_\theta^{\pi}(s)}{\partial s^i \partial s^j}\bigg|_{s_t}\right) - \tilde{V}_\theta^\pi(s_t)\right)^2
\end{aligned}
$$
</div>
</v-click>

<v-click>
<figure style="position: absolute; top: 74%; left: 35%">
  <img src="./figures/model_dependent.png" style="width: 62%;">
</figure>
<div style="font-size: 0.8em; position: absolute; top: 81%; left: 20% ; width: 625px;">
モデルを埋め込むことはできたが, 目的関数にモデルが現れるようになるため, このままだとモデルを知らないと学習できない。
</div>
</v-click>

<v-click>
<div style="font-size: 0.8em; position: absolute; top: 85%; left: 31% ;">
$$
\begin{aligned}
V^\pi(s_t) &= \frac{1}{\gamma}\mathbb{E}_{P_\pi}\left[\text{entirely computable from trajectories}\right]
\end{aligned}
$$
</div>
</v-click>


---
layout: default
headerEnable: true
headerTitle: Our Approach - Method
headerLogo: figures/utokyo.png
---

## Main result1

モデルの推定に必要な普遍推定量を見つけたことで, 連続性を埋め込んだ目的関数をサンプルのみから学習できるようになった。

<div style="font-size: 0.8em; position: absolute; top: 28%; left: 28% ;">
$$
\begin{aligned}
\mathbb E_{P_{\pi}}\left[\mu^i(s_t, A_t)\right] &= \underset{\Delta t\rightarrow 0}{\lim}\mathbb E_{P_{\pi}}\left[\frac{S_{t+\Delta t}^i-s_t^i}{\Delta t}\right] \\
\mathbb E_{P_{\pi}}\left[[\sigma(s_t, A_t)\sigma^\top(s_t, A_t)]^{ij}\right] &= \underset{\Delta t\rightarrow 0}{\lim}\mathbb E_{P_{\pi}}\left[\frac{(S_{t+\Delta t}^i - s_{t}^i)(S_{t+\Delta t}^j - s_{t}^j)}{\Delta t}\right]
\end{aligned}
$$
</div>

<div class="relative h-[300px]">
  <hr class="absolute top-[100px] left-[2%] w-[96%] border-t border-gray-300" />
</div>

<v-click>
<div style="font-size: 0.8em; position: absolute; top: 54%; left: 2% ;">
$$
\begin{aligned}
\mathcal{L}(\theta) &\ \ \ = \left(\frac{1}{\gamma}\mathbb{E}_{P_\pi}\left[\rho(s_t, A_t)+\sum_{i=1}^{n} \mu^i(s_t, A_t)\frac{\partial \tilde{V}_\theta^{\pi}(s)}{\partial s^i} \bigg|_{s_t}+ \frac{1}{2} \sum_{i=1}^{n} \sum_{j=1}^{n}[\sigma(s_t, A_t)\sigma^\top(s_t, A_t)]^{ij}\frac{\partial^2 \tilde{V}_\theta^{\pi}(s)}{\partial s^i \partial s^j}\bigg|_{s_t}\right] - \tilde{V}_\theta^\pi(s_t)\right)^2 \\
&\overset{\begin{array}{c}\scriptsize \text{Main} \\ \scriptsize \text{result}\end{array}}{=} \left(\frac{1}{\gamma}\underset{\Delta t\rightarrow 0}{\lim}\mathbb{E}_{P_\pi}\left[\rho(s_t, A_t)+\sum_{i=1}^{n} \frac{S_{t+\Delta t}^i-s_t^i}{\Delta t}\frac{\partial \tilde{V}_\theta^{\pi}(s)}{\partial s^i} \bigg|_{s_t}+ \frac{1}{2} \sum_{i=1}^{n} \sum_{j=1}^{n}\frac{(S_{t+\Delta t}^i - s_{t}^i)(S_{t+\Delta t}^j - s_{t}^j)}{\Delta t}\frac{\partial^2 \tilde{V}_\theta^{\pi}(s)}{\partial s^i \partial s^j}\bigg|_{s_t}\right] - \tilde{V}_\theta^\pi(s_t)\right)^2 \\
\Longrightarrow\tilde{\mathcal{L}}(\theta) &\overset{\begin{array}{c}\scriptsize \text{for sufficiently} \\ \scriptsize \text{small }\Delta t > 0\end{array}}{\approx} \left(\frac{1}{\gamma}\left(\rho(s_t, A_t)+\sum_{i=1}^{n} \frac{s_{t+\Delta t}^i-s_t^i}{\Delta t}\frac{\partial \tilde{V}_\theta^{\pi}(s)}{\partial s^i} \bigg|_{s_t}+ \frac{1}{2} \sum_{i=1}^{n} \sum_{j=1}^{n}\frac{(s_{t+\Delta t}^i - s_{t}^i)(s_{t+\Delta t}^j - s_{t}^j)}{\Delta t}\frac{\partial^2 \tilde{V}_\theta^{\pi}(s)}{\partial s^i \partial s^j}\bigg|_{s_t}\right) - \tilde{V}_\theta^\pi(s_t)\right)^2
\end{aligned}
$$
</div>
</v-click>

---
layout: default
headerEnable: true
headerTitle: Our Approach - Method
headerLogo: figures/utokyo.png
---

## Interpretation

**Classical TD Loss:**

$\tilde{\mathcal{L}}(\theta)=\sum_{t=1}^{T}(\rho\Delta t + e^{-\gamma\Delta t}V_\theta(s_{t+1})-V_\theta(s_t))^2$



**Proposed TD Loss:**

$\tilde{\mathcal{L}}(\theta) = \sum_{t=1}^{T}\small{\left(\frac{1}{\gamma}\left(\rho(s_t, A_t)+\sum_{i=1}^{n} \frac{s_{t+\Delta t}^i-s_t^i}{\Delta t}\frac{\partial \tilde{V}_\theta^{\pi}(s)}{\partial s^i} \bigg|_{s_t}+ \frac{1}{2} \sum_{i=1}^{n} \sum_{j=1}^{n}\frac{(s_{t+\Delta t}^i - s_{t}^i)(s_{t+\Delta t}^j - s_{t}^j)}{\Delta t}\frac{\partial^2 \tilde{V}_\theta^{\pi}(s)}{\partial s^i \partial s^j}\bigg|_{s_t}\right) - \tilde{V}_\theta^\pi(s_t)\right)^2}$

<figure style="position: absolute; top: 58%; left: 15%">
  <img src="./figures/TD_pic.png" style="width: 60%;">
  <figcaption style="font-size: 1.2em; position: absolute; top: 100%; left: 10%; font-size: 0.8em; white-space: nowrap;">
  <strong>Classical TD Loss</strong>
  </figcaption>
</figure>

<figure style="position: absolute; top: 58.9%; left: 35%">
  <img src="./figures/dTD_pic.png" style="width: 60%;">
  <figcaption style="font-size: 1.2em; position: absolute; top: 100%; left: 10%; font-size: 0.8em; white-space: nowrap;">
  <strong>Proposed TD Loss</strong>
  </figcaption>
</figure>

<div style="font-size: 0.9em; position: absolute; top: 57%; left: 58%; width: 320px;">
<strong>従来のTDと提案したdTDの定性的な違い;</strong>
それぞれの手法は図の赤い部分を見てパラメータを調整する。TDの目的関数は<span style="color: rgb(220, 20, 60);">Vの値</span> を使って最適化する一方で, dTDは<span style="color: rgb(220, 20, 60);">Vの勾配とヘッシアンを</span>使って最適化を行うため, 価値関数が滑らかになるような作用がある。
</div>


---
layout: default
headerEnable: true
headerTitle: Our Approach - Analysis
headerLogo: figures/utokyo.png
---

## Convergence Analysis(Main result2)

**Classical TD:**
$$\begin{aligned}&V_{i+1}^\pi(s_t) = (TV_{i})(s_t):=\mathbb{E}_{P_\pi}\left[r(s_t, A_t)+\gamma V_i^\pi(S_{t+1})\right] \\ &\|TV^\pi-TU^\pi\|_\infty\leq\gamma\|V^\pi-U^\pi\|_\infty\:(0<\gamma<1)\end{aligned}$$

**dTD:**
$$\begin{aligned}&V_{i+1}^\pi(s_t) = (\tilde{T}V_{i})(s_t):=\frac{1}{\gamma}\mathbb{E}_{P_\pi}\left[\rho(s_t, A_t)+\sum_{i=1}^{n} \mu^i(s_t, A_t)\frac{\partial V_i^{\pi}(s)}{\partial s^i} \bigg|_{s_t}+ \frac{1}{2} \sum_{i=1}^{n} \sum_{j=1}^{n}[\sigma(s_t, A_t)\sigma^\top(s_t, A_t)]^{ij}\frac{\partial^2 V_i^{\pi}(s)}{\partial s^i \partial s^j}\bigg|_{s_t}\right] \\ &\|\tilde{T}V^\pi-\tilde{T}U^\pi\|_{H^{-1}(S)}\leq\frac{1}{\gamma}\left(\sum_{i=1}^2\|\nabla^i\mu\|_{L^\infty}+\sum_{i=1}^3\|\nabla^i\sigma\|_{L^\infty}\right)\|V^\pi-U^\pi\|_{H^{-1}(S)}\:(0<\gamma<\infty)\end{aligned}$$


**(Efficient Computation)**

$$\left\langle\Delta s_t, \frac{\partial^2 V}{\partial s^2}\bigg|_{s_t}\Delta s_t\right\rangle=\left\langle\Delta s_t, \frac{\partial}{\partial s}\left\langle\frac{\partial V}{\partial s},\Delta s_t\right\rangle\bigg|_{s_t}\right\rangle$$


<figure style="position: relative; top: -90%; left: 80%; width: 120px; text-align: center;">
    <img src="./figures/convergence.png" style="width: 100%;">
</figure>

<style>
.slidev-vclick-hidden {
  display: none;
}
</style>


---
layout: default
headerEnable: true
headerTitle: Our Approach - Experiment
headerLogo: figures/utokyo.png
---

## Experimental Design


<figure style="position: absolute; top: 22%; left: 10%">
  <img src="./figures/brax_logo.png" style="width: 20%;">
</figure>

<figure style="position: absolute; top: 15%; left: 27%">
  <img src="./figures/hc.gif" style="width: 50%;">
</figure>

<figure style="position: absolute; top: 15%; left: 44%">
  <img src="./figures/ant.gif" style="width: 50%;">
</figure>

<figure style="position: absolute; top: 15%; left: 61%">
  <img src="./figures/hm.gif" style="width: 50%;">
</figure>

<figure style="position: absolute; top: 50%; left: 50%">
  <img src="./figures/vertical_line.png" style="width: 50%;">
</figure>

<v-click>
<div style="font-size: 1.0em; position: absolute; top: 52%; left: 4%; width: 320px;">
  <strong>Modification for discrete environment compatibility</strong>
</div>
<div style="font-size: 0.8em; position: absolute; top: 60%; left: 5% ;">
$$
\begin{aligned}
&\int_{0}^\infty \text{e}^{-\gamma t}\rho(s_t, a_t)dt\approx \sum_{k=0}^\infty \text{e}^{(-\gamma\Delta t)k}\rho(s_{k\Delta t}, a_{k\Delta t})\Delta t \\
&\Longrightarrow \rho(s_t, a_t)=\frac{r(s_t, a_t)}{\Delta t}\text{ and }\rho(s_t, a_t)=-\frac{1}{\Delta t}\log{(\gamma_{\text{discrete}})}
\end{aligned}
$$
</div>
</v-click>

<v-click>
<div style="font-size: 1.0em; position: absolute; top: 52%; left: 54%; width: 320px;">
  <strong>Add noise to mimic stochastic environment</strong>
</div>
<div style="font-size: 0.8em; position: absolute; top: 63%; left: 60% ;">
$$
\begin{aligned}
&\mathbf{s}_i\leftarrow \mathbf{s}_i + \nu |\mathbf{s}_i|\times\text{noise}\\
&\nu\in\{0.0, 0.01, 0.05\},\:\text{noise}\sim\mathcal{N}(0,1)
\end{aligned}
$$
</div>
</v-click>


---
layout: default
headerEnable: true
headerTitle: Our Approach - Experiment
headerLogo: figures/utokyo.png
---

## Results

<figure style="position: absolute; top: 20%; left: 30%">
  <img src="./figures/result.png" style="width: 65%;">
</figure>


<figure style="position: absolute; top: 38%; left: 21%">
  <img src="./figures/hc.gif" style="width: 35%;">
</figure>

<figure style="position: absolute; top: 54.8%; left: 21%">
  <img src="./figures/ant.gif" style="width: 35%;">
</figure>

<figure style="position: absolute; top: 71.6%; left: 21%">
  <img src="./figures/hm.gif" style="width: 35%;">
</figure>

---
layout: default
headerEnable: true
headerTitle: Summary
headerLogo: figures/utokyo.png
---

## Summary

- 確率最適制御がターゲットとするHJB方程式(ベルマン方程式の連続版)をモデルフリーで学習する強化学習手法を提案した。モデルを知らなくてもモデルの連続性を活用して学習することが可能。
- 理想的な行進ではダイナミクスが滑らかであるほど収束が速いことを示した。
- ロボットのような工学的な応用だけでなく, 近年研究されている確率最適制御を用いたDiffusion Modelのチューニング[1][2]などにも利用可能(現在の手法はbackward processをモデル化するため余計にモデルを学習しているがこの過程を無くせる)。

<div style="font-size: 0.7em; text-align: left; position: absolute; bottom: 10px; left: 20px;">
[1] Masatoshi Uehara et al.(2024) Understanding Reinforcement Learning-Based Fine-Tuning of Diffusion Models: A Tutorial and Review. arXiv:2407.13734, 2024.<br>
[2] Wenpin Tang.(2024) Fine-tuning of diffusion models via stochastic control: entropy regularization and beyond. arXiv:2403.06279, 2024.
</div>

---
layout: section
subject: 研究計画
---

# 博士課程の研究計画

---
layout: default
headerEnable: true
headerTitle: 研究計画
headerLogo: figures/utokyo.png
---

**研究概要**

強化学習のNNを用いた関数近似による汎化能力(未知の入力にも正しい出力を行う能力)の研究を行う。

**汎化誤差解析**
<figure style="position: absolute; top: 35%; left: 7%; width: 600px;">
  <img src="./figures/gene.png" style="width: 65%;">
</figure>
<figure style="position: absolute; top: 35%; left: 55%; width: 600px;">
  <img src="./figures/rl_frame.png" style="width: 65%;">
</figure>

---
layout: default
headerEnable: true
headerTitle: 研究計画
headerLogo: figures/utokyo.png
---

**当該分野の現状の課題**

<figure style="position: absolute; top: 25%; left: 3%; width: 600px;">
  <img src="./figures/mdp_structures.png" style="width: 65%;">
</figure>

<div style="font-size: 0.8em; text-align: left; position: absolute; top: 25%; left: 44%; width: 500px;">
- 図右下のように, MDPに何の構造も仮定しなければ汎化が不可能な例を構成することができる。教師あり学習のように仮説集合の大きさを制御しても, 報酬という局所的な要素があるためこのような例が構成できる。<br>
- 状態空間のサイズが有限であれば汎化可能(図右上)<br>
- 状態遷移, 報酬, 関数近似器のすべてに線型性を仮定すれば汎化可能。<br>
- 状態空間は無限だが, 潜在的に有限の状態空間を仮定するBlock MDPという構造も存在する。この制約の下では非線形関数近似で汎化可能。
- 近年, 教師あり学習の汎化誤差解析で研究されている平均場理論をもちいた深層強化学習の解析も存在するが, 状態空間のサイズが有限であることを要請したり, 価値関数に制約を課しており, 具体的にどのようなMDPを構成すれば汎化可能なのかは明らかになっていない。

以上の課題を踏まえ、本研究では以下を目標とする：
- 状態空間のサイズ無限
- 非線形関数近似に対応する, できるだけ緩いMDPの構造を明らかにする
- 明らかにしたMDPに対して最適な探索を考える
- (1)価値関数の推定と(2)方策の最適化を統一的に解析する
</div>

---
layout: default
headerEnable: true
headerTitle: 研究計画
headerLogo: figures/utokyo.png
---

**年次計画**

**1年目**<br>
**前半:** **価値関数の推定において汎化可能な状態遷移の構造を明らかにする。** 非線形関数近似を用いた解析では状態サイズが本質的に有限であることを要求するため, 無限と有限をつなぐ解析の道具を使うことや, それが無理であればLQRを拡張したControlled Diffusion(修士の研究対象)を仮定する。<br>
**後半:** **方策最適化の汎化誤差の上限の導出をおこなう。** 現在, 方策最適化は自然勾配法を用いた線形関数近似のもとでは状態空間のサイズに依存せずに大域的最適解に収束することがわかっている。自然勾配法のどのような性質が状態空間のサイズに依存しない解析を可能にするのかを理解し, 平均場理論と組み合わせて解析を行うことを想定している<br>

**2年目**<br>
**前半:** 1年目前半と後半の成果を組み合わせて価値関数の推定が要求するMDPの構造の下で方策最適化の汎化誤差解析を行う。<br>
**後半:** 2年目前半で得られた結果を用いて価値関数の推定の汎化誤差解析を行い, 価値関数の推定と方策最適化を統一的に解析する。<br>

**3年目**<br>
2年目までに得られたMDPの構造の下での効率的な探索や応用研究を行う。

---
layout: section
subject: Thank you
hideInToc: true
---
