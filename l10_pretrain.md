# Pretrain model - BERT, GPT,  


 Normal 
---
  f_theta_T1 ->  question-answering 
  f_theta_T2 -> sentiment analysis 
  f_theta_T3 -> dialuge(eg. chatbot) 


Language modeling 
 - global - generalize neural network with really huge corpus
    generalize task


- fine-tuning because we dont trained from scrath 

- Transfering learing is the whole process create pretrained model to train on generalize task on large dataset  
  

 Common industry practices
---
1. low learing rates especilay earlier layers
   eg. gramar, dependcy 

   because fundamental underline meachanism 


  meta vs multi task learing is the future 
    that have same dream 
        
  multi-task

  QA, SA combine into huge show the same structure 
       show the same structure input and output across all the tasks

   Mixure of Expert (Moe)

    * you trained task at once but you break branch

    input -> earlier layers -> we branch out and we specific NN for different tasks

    earlier layers : capture low level basic information
    
    * problem -> some task is easier than other tasks or more difficult
     
       eg. let's say sentiment 90, question acc 48

   soln
    
    1)  put more difficult task in one batch size 

    2) loss = sum of each loss 
        i ~ index of some tasks
        change it to sum wiLi give higher weight for the loss

 Meta learning -> few shot learing is the same term 
---
 
 * Learing how to learn

 in computer vision 
   
   eg. Resnet (2015) 

 in NLP (2018)
   eg. BERT, GPT, T5

 Pre-trained objectives
---
 * ask the model do many thing by masking  best generalize task is language modeling tasks randomly blank (masked) 

 * if generalize task is LM 
    eg. I love deep ----- 
        if every time we trained we should masked attentions
              deep will have score between I and love 
                  L decoder
  * generalize task -> masked LM -> we can predict any word in between not only next word like langugage models
       L normal attention -> encoder ways

  *   

