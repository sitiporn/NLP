# Language Model and RNN
---
 
  why do we need RNN ? 
 
 - language model is task is not whole NLP 

 - compute prob distribution  of the next sentecne x_t+1


 n-gram Language Models
  
  n-gram LM : pre-Deep learing 

 Generative text with an n-gram LM
  - no longer in training phase 
  - inference model -> testing mode
 
 Decoding algorithm 
  1) pick best one argmax
  2) random  pick (sampling)
  3) search (beam search) 

  what is best probable word in the inference mode -> decoding  
 
  * the more N-gram -> the language model more smarter 
     - but is never enough 

  Fixed Window Neural LM 

  * remaing problems 
     - Fixed window is too small
    
    we need a neural architecture that any len input

 RNN
---
 fixed: storage problems, no need to to store all observed n-grams 

 core idea: apply the same weight W repeatedlly

 if use linear layer we need to specify the len -> this is not ok  -> use RNN instead 

     Weight : [1 2 3 4 ]
     words : [1 2 3 4]

     so each word weight can only activate on each area that word product with no interaction between words
     
 no interaction between word is independly between previous and next word 

 why not use single Weight W and carry information ->  carry some interaction between words 
  solve 
 
 1) unlimited seq in Theory
 2) allow interaciotns between prev and next word

 * Remaing problem
   - Recurrent is slow 
   - difficult to access information from very far is gone 

 EEG may not relevance to use RNN only 

 * teacher forcing  
     dont use previous prediction as i/p of current word

  RNN - generating text 
---
  - this is not teacher forcing mode but this is infering or testing mode 
  - decoding when use language model to generate something   

  Evaluation of LM 
---
  * the lower the better 
    
 

  

     
