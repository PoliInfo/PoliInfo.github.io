---
# Edit theme's home layout instead if you wanna make some changes
# See: https://jekyllrb.com/docs/themes/#overriding-theme-defaults
layout: default
---
# [](#whats-new)What's New


* Released the website to the public, Dec. 21, 2017

See [update history](https://github.com/PoliInfo/PoliInfo.github.io/commits/master)

# [](#overview)Overview

The goal of the QALab-PoliInfo(Question Answering Lab for Political Information) task at NTCIR 14 is aimed at complex real-world question answering (QA) technologies, to extract structured data on the opinions of assemblymen, and the reasons and conditions for such opinions, from Japanese regional assembly minutes.
We provide the Japanese Regional Assembly Minutes Corpus as the training and test data, and investigate appropriate evaluation metrics and methodologies for the structured data as a joint effort of the participants.

QA using Japanese regional assembly minutes has the following challenges to consider:
1. Comprehensible summary of a topic,
2. Beliefs and attitudes of assemblymen,
3. Mental spaces for other assemblymen,
4. Contexts, including reasons,
5. Several topics in a speech,
6. Colloquial Japanese including dialect and slang.  

In addition to QA technologies, this task will contribute to the development of a semantic representation, context
understanding, information credibility, automated summarization, and dialog systems.

# [](#task)Task

Extraction taskとSummarization taskの２通りのタスクを行う。

### Extraction Task

Extraction Taskでは、ある議員の議会会議録中の「発言」とその発言の「要約」の組が与えられる。
参加者は、要約に書かれた内容（意見）に関連する「根拠」や「条件」などに対応する記述を発言から抽出する。
本タスクの特徴は、抽出対象に「固有表現などよりも長い文字列」が含まれることである。

Extraction taskは、新聞記事やマイクロブログなどにおいて「A議員は〇〇と主張した」といった二次情報（本タスクの「要約」が該当）に対して、発言したとされる一次情報（本タスクの「発言」が該当）の中から、その関連情報を提示することに相当する。
引用における問題には、条件節の削除など発言の一部が切り取られたことにより、発言者の本来の意図とは異なった印象を読者に与えてしまうといった問題がある。
そのような問題を解決するために、引用された発言の周辺文脈（根拠や条件など）を提示することが必要であり、本タスクはそれに該当する。

* Input:  議会会議録中の「発言」とその発言の「要約」

* Output:  要約中の意見の「根拠」や「条件」に対応する記述


### Summarization Task

Summarization Taskでは、ある議員の議会会議録中の「発言」と要約の「制限文字数」が与えられる。
参加者は、発言中の「意見」、「根拠」、「条件」などが一読して分かるような要約を作成する。

Summarization Taskは、読者に誤解を与えないような引用とは何かに主眼を

* Input: A Sentence Sequence in Transcript  

ex.  
---
260618_304,初めに、認知症対策について質問いたします。  
260618_305,都の最新の推計によれば、何らかの認知症状がある高齢者は、現在都内で約三十八万人おられ、十一年後の二〇二五年には約六十万人、実に高齢者人口の約二割まで急増するとされています。  
260618_306,認知症は、脳の器質障害により、社会生活の基本となる認知機能が低下する疾患であり、患者本人はもとより、家族や地域社会にも広く影響を及ぼす、超高齢時代特有のすぐれて今日的な疾患といえます。  
260618_307,今後は、単身や夫婦のみの高齢者世帯の増加も加速することなどから、患者や介護する家族が安心して暮らし続けることができる体制の整備は都政の最重要課題の一つです。  
260618_308,都は、平成十九年度に認知症対策推進会議を設置し、国に先駆けてさまざまな施策を実施してきたことは評価いたしますが、東京を世界一の福祉先進都市にするには、舛添知事のさらなるリーダーシップが求められます。  
260618_309,ご所見をお伺いいたします。  
260618_310,次に、認知症の高齢者行方不明問題についてであります。  
260618_311,先日、全国の警察が把握した認知症の行方不明高齢者の届け出が、昨年一年間で一万人を超え、都内でも三百八人の届け出があったとの報道がありました。  
260618_312,認知症の方が徘回等で行方不明になった場合、家族は警察に捜索依頼を行います。  
260618_313,また、警察は、身元不明者を保護した場合、二十四時間以内に地元区市町村へ引き継ぐことになっています。  
260618_314,都は現在、区市町村からの依頼に基づき、家族から捜索依頼のあった行方不明者や、警察から引き継がれた身元不明者の情報を区市町村や近隣県に情報提供し、発見に役立ててもらう取り組みを行っています。  
260618_315,今後、ますます認知症による行方不明者はふえるものと懸念されます。  
260618_316,ご家族の苦しみを少しでも軽減するため、都は積極的に情報を掌握し、より広域的に情報を共有できるシステムを整備すべきです。  
260618_317,見解を求めます。  
260618_318,次に、認知症の患者とその家族を支える地域の対応力の向上についてであります。  
260618_319,杉並区にある浴風会病院は、都の認知症疾患医療センターの一つとして、診断を初め、専門相談や地域における医療と介護の連携づくりなど、さまざまな取り組みを行っています。  
260618_320,また、早期発見、診断のため、アウトリーチの取り組みも昨年度から実施しています。  
260618_321,直接スタッフの方からお話を伺いましたが、医師や看護師、精神保健福祉士等から成る専門職のチームが、病院を受診したがらない高齢者の方の自宅を一軒一軒訪問し、早期の受診や支援につなげておられるとのことでした。  
260618_322,また、コーディネーターを初めとする地域関係者の認知症に対する理解が鍵ともいわれていました。  
260618_323,こうした先進的な取り組みは都内の各地域に広げていくべきですが、そのためには、医療機関や地域包括支援センターなどの関係機関や認知症コーディネーターを初めとする地域の関係者の対応力を向上させ、連携を強化させていく必要があると考えます。  
260618_324,見解を求めます。  
260618_325,こうしたこととあわせ、一般都民の理解を深めることもまた重要です。  
260618_326,先ほど指摘した行方不明問題についても、近隣住民や商店街など地域の人たちが認知症に関し幅広く理解していれば、早目に気がつき、声をかけ、保護することも可能となります。  
260618_327,地域社会全体で患者や家族を支えていく取り組みが重要となってまいりますが、都の見解を求めます。  
260618_328,この課題の最後に、認知症医療の充実について伺います。  
260618_329,これまで指摘してきたとおり、認知症患者や家族の支援は非常に多岐にわたりますが、やはり重要なのは、適切な診断、治療を受けられる医療体制の確立です。  
260618_330,この点、都立松沢病院は、認知症疾患医療センターであり、都内では数少ない専門医療を行う入院病棟を備えております。  
260618_331,患者から目を離せない認知症の介護は、家族にとって身体的にも精神的にも大きな負担であり、適切な入院治療に期待するところは大きいものがあります。  
260618_332,都全域を対象に精神科の専門医療を提供する都立松沢病院において、認知症医療の充実を図るべきと考えますが、見解を求めます。  
---

* Output: 
ex.  
---
認知症対策  
体制整備は都政の最重要課題の一つ。知事の更なるリーダーシップを。  
---



# [](#collection-and-tools) Collection and Tools

TBA

# [](#important-dates) Important Dates

- Feb 20, 2018:  Kickoff meeting in NII (room 1901, 1902)  
- Mar 14, 2018:  1st round table meeting at Okayama Convention Center in NLP 2018  
- Mar 15, 2018: Task Registration Due  
- Jun 2018: Dataset Release  
- Jul 2018: Dry Run  
- Nov 2018: Formal Run  
- Dec 20, 2018: Evaluation Result Release  
- Dec 20, 2018: Task overview paper release (draft)  
- Feb 1, 2019:  Submission due of participant papers  
- Mar 1, 2019:  Acceptance notification  
- Jun 2019: NTCIR-14 Conference & EVIA 2019 in NII, Tokyo  

# [](#organizers) Organizers

- Noriko Kando, National Institute of Informatics, Japan and SOKENDAI, Japan
- Madoka Ishioroshi, National Institute of Informatics, Japan
- Teruko Mitamura, Carnegie Mellon University, USA
- Yasutomo, Kimura, Otaru University of Commerce, Japan and RIKEN, Japan
- Hideyuki Shibuki, Yokohama National University, Japan
- Kotaro Sakamoto, Yokohama National University, Japan and National Institute of Informatics, Japan

## Advisers
- Tatsunori Mori, Yokohama National University, Japan

# [](#publications) Publications

# [](#contact-us) Contact Us

* [q...@nii.ac.jp](https://www.google.com/recaptcha/mailhide/d?k=01O9zbkTiGrK94vkzok6UTlA==&c=O9PnuKWAEXZJ-9F2iQ1s3NCEpYO4jMMUhYsmRhdCk0c=) 

# Misc
## Logo
<img src="qalab.png" alt="QA Lab Logo" title="QA Lab Logo" style="width: 200px;"/>

## Past QA Lab

- [NTCIR-13 QA Lab-3 (2016-2017)](http://research.nii.ac.jp/qalab/)
- [NTCIR-12 QA Lab-2 (2015-2016)](http://research.nii.ac.jp/qalab/qalab2/index.html)
- [NTCIR-11 QA Lab-1 (2013-2014)](http://ntcir.nii.ac.jp/QA-Lab/)

## NTCIR-14

- [English](http://research.nii.ac.jp/ntcir/ntcir-14/index.html)
- [Japanese](http://research.nii.ac.jp/ntcir/ntcir-14/index-ja.html)
