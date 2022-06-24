# 한국어 어휘의미망의 거리 기반 그래프 임베딩 모형 
(alias. Korlex, http://korlex.pusan.ac.kr/)

<br>

- 본 결과물은 부산대에서 개발한 한국어 어휘의미망을 심층학습(deep learning)에 적용이 가능하도록 네트(net) 구조의 어휘의미망 상에서 단어 간의 거리를 측정하여 벡터(vector)로 임베딩 한 것입니다. 본 연구의 그래프 모형은 word2vec(skip-gram) 방식으로 학습하였습니다.
<br><br>


## <b>한국어 어휘의미망(alias. Korlex)</b> 

<br>

- 한국어 어휘 의미망은 미국 프린스톤 대학교의 인지심리학자 밀러(George A. Miller)와 동료에 의해 개발된 인간 언어를 대상으로 구축한 최소 어휘 의미망인 영어 워드넷(WordNet, PWN)을 부산대학교에서 대치 및 추가 구축한 것입니다. 한국어 어휘 의미망은 명사, 동사, 형용사, 부사, 수분류사로 구성되어 있으며, 본 연구에서는 한국어 어휘의미망에서 가장 큰 비중을 갖는 품사인 명사를 대상으로 그래프 임베딩 학습을 하였습니다. 한국어 어휘의미망의 전체 데이터를 얻기 위해서는 사이트 (http://korlex.pusan.ac.kr/) 에 접속하여 승인 페이지를 통해서 사용 할 수 있습니다. 개인 연구 이외의 용도로는 따로 비용이 발생합니다.
<br>

||명사|형용사|동사|부사|수분류사|전체|
|:---:|---:|---:|---:|---:|---:|---:|
|단어 수|113,082|22,559|23,611|3,699|1,611|164,562|

<br><br>

## <b>거리 측정 방식</b> 

<br>

- [Jiang-Conrath](https://www.gabormelli.com/RKB/Jiang-Conrath_Similarity_Measure)
- [Leacock-Chodorow](http://www.gabormelli.com/RKB/Leacock_Chodorow_Similarity_Measure)
- [Shortest path](https://en.wikipedia.org/wiki/Shortest_path_problem)
- [Wu-Palmer](https://www.gabormelli.com/RKB/Wu-Palmer_Similarity_Measure)
<br><br>


## <b>학습 코드</b> 

<br>

- 본 연구는 [Making Fast Graph-based Algorithms with Graph Metric Embeddings](https://aclanthology.org/P19-1325/)의 워드넷 학습 코드를 기반으로 한국어 어휘의미망에 적용을 하였습니다. (https://github.com/uhh-lt/path2vec)
<br><br>

## <b>한국어 적용 형식</b> 

<br>

- 형식 : [단어].[품사].[표준국어대사전 의미번호]<br>
- 예


```
근린.n.01
근방.n.01
부근.n.03
```

<br><br>

## <b>모형 배포 정보</b>

<br>

|배포 파일명|설명|
|:--:|--|
|[Jiang-Conrath 기반 모형](http://pnuailab.synology.me:5000/sharing/xpnQTAq40)|768 vector, 0.001 learning rate, 3 neighbors count|
|[Leacock-Chodorow 기반 모형](http://pnuailab.synology.me:5000/sharing/pMtc5Iufv)|768 vector, 0.001 learning rate, 3 neighbors count|
|[Shortest path 기반 모형](http://pnuailab.synology.me:5000/sharing/iLIZJ80eI)|768 vector, 0.001 learning rate, 3 neighbors count|
|[Wu-Palmer 기반 모형](http://pnuailab.synology.me:5000/sharing/iLIZJ80eI)|768 vector, 0.001 learning rate, 3 neighbors count|

<br><br>

# <b>학습 모형 유사도 및 단어 분별 성능</b>

<br>

|시스템 명|Korlex|고정 의미 성능<br>(static)|유동 의미 성능<br>(dynamic)|
|:--:|:--:|:--:|:--:|
|Jiang-Conrath 기반 모형|86%|40%||
|Leacock-Chodorow 기반 모형|82%|27%||
|Shortest path 기반 모형|50%|61%||
|Wu-Palmer 기반 모형|50%|61%||

<br><br>
