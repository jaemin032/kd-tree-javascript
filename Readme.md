# 챗봇의 Q&A데이터 시각화

* [Demo](http://jaemin032.github.io/kd-tree-javascript/examples/basic/) - animated multiple nearest neighbour search

## 데이터
챗봇의 Q&A데이터를(https://github.com/songys/Chatbot_data) 다운 받아 읽어들이고 단어들을 추출한다.

## 좌표 변환
단어들을 2차원 공간에서 시각화하기 위해서는 좌표값이 필요하다. 우선 단어들을 Fasttext(https://fasttext.cc/)를 활용하여 300개의 숫자로 이루어진 벡터값으로 변환할 수 있다. 
 300개를 직접적으로 사용할 수는 없으므로 차원축소 과정을 거쳐야만 한다. PCA를 활용하여 2차원의 벡터로 변환한다. Html의canvas에 표현할 예정이므로 차원 축소 과정을 거친 뒤에는 0과 1사이의 값으로 정규화한다.

## 유사단어 시각화

![alt text](https://github.com/jaemin032/kd-tree-javascript/blob/master/images/word_visualization.png)


이제 javascript에서 kd-tree 라이브러리(https://github.com/ubilabs/kd-tree-javascript)를 활용하여 단어들을 시각화할 수 있다. 20개의 공이 각자 가장 가까운 점 5개를 추적하면서 빠르게 움직이고 있는데도 프레임 수가 300이상을 유지하는 것을 볼 수 있다. 이는 각 단어들의 좌표값이 kd-tree를 활용하여 보관되고 있고 neighbor들을 구하는데에 시간 복잡도가 낮기 때문에 가능한 일이다. 




