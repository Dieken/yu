<!-- omit in toc -->
# 天碼

- [簡介](#簡介)
- [規則](#規則)
- [字根練習](#字根練習)

## 簡介

天碼是一個表形碼輸入方案，由宋天研製。特點有：四碼定長、純字形、雙編碼、繁簡通打[^fanjian]等。因為其大碼錶形，小碼取音的設計哲學，易學性極高。QQ討論群：631302614

注意，本拆分查詢中不顯示首根小碼補碼。

<script setup>
import Search from '@/search/FetchSearch.vue'
import CharTrain from "@/train/CharTrain.vue"
import ZigenTrain from "@/train/ZigenTrain.vue"
</script>

<Search chaifenUrl="/chaifen-tianma.csv" zigenUrl="/zigen-tianma.csv" :supplement="false" />

## 規則

天碼共約 500 字根，歸類後約 250，在 26 鍵上，依據其形態，對應到近似的拉丁字母上，形成規則排布。

::: tip 例
`人` `八` 像字母 A，故而排在 A 鍵上。
`丁` `下` `不` 像字母 T，故而排在 T 鍵上。
:::

每個字根還有一個小碼，為其漢語拼音首字母。生僻字根或無讀音字根小碼為 v。

其編碼規則類似於宇碼，總結如下：

- 依次取首、次、三、末根
- 不足四碼補末根小碼（拼音）
- 仍不足四碼補首根小碼（若是 v 則可以省略）

::: info 編碼規則公式化

單字拆分成若干字根後，最多取四根。假設首次三末根編碼為 Aa Bb Cc Zz。則單字編碼規則為：

- 單字根字 Zz
- 兩字根字 AZza
- 三字根及以上字 ABCZ

單行定義為：ABCZza\[:4\]
:::

## 字根練習

<ZigenTrain name="tianma" zigenUrl="/zigen-tianma.csv" :range="[0,]" mode='both' />

!-- ## 單字練習

為了降低學習難度，練習中，不補首根小碼。

<CharTrain name="tianma" zigenUrl="/zigen-tianma.csv" :range="[0,1000]" :supplement="false" /> --

[^fanjian]: 一般認為單一碼錶繁簡聯合選重率小於萬分之五十即具有繁簡通打特性。