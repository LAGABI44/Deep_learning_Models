# Longformer model
캐글 : Feedback Prize - Evaluating Student Writing


***
### Longformer model의 문제점
1. TPU 환경에서의 오류
=> 롱포머 및 리포머는 파이토치/XLA에서 작동 불가   
https://github.com/huggingface/transformers/issues/6693

***
### 기타 사항
![image](https://user-images.githubusercontent.com/96757866/153583492-b50058af-fa98-4fc7-91bb-6283d7bddfd6.png)

1. [논문](https://arxiv.org/pdf/2004.05150.pdf) 상에서 긴 document를 다루는 task들에 대해 Longformer를 base로한 Roberta 모델이 더 좋은 성능을 내는 것을 보여줌
2. 단일 roberta 모델의 경우 longformer보다 낮은 성능을 보임   
https://www.kaggle.com/c/feedback-prize-2021/discussion/297577
4. longformer 모델 1개보다 2개의 longformer모델을 사용할 경우 성능이 훨씬 좋음   
kaggle의 base 코드 참고(1개의 lonformer model CV 0.633 / 2개의 CV 0.690)



***
### Reference
1. 논문 리뷰1 : https://pko89403.github.io/post/longformer/
2. 논문 리뷰2 : https://medium.com/@eyfydsyd97/%EB%85%BC%EB%AC%B8-%EB%A6%AC%EB%B7%B0-longformer-the-long-document-transformer-e9ade1980536
3. longformer model github : https://github.com/allenai/longformer 
