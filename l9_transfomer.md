# Transfomers

 * W always no interaction between words 
 * W become big as sentence is low 


 RNN
---
  - W is shared 
  - W is fixed 

  problem
 - vanish grad or long term dependencies 


 GRU
--
 allow alternative path for grad to flow

 problem

 - use last hidden -> it may not capture all inforamtion 
 - solve  -> elelment wise for all hidden state mean or max 
    
    
 RNN + attention
---
  -  elem wise mean vs attention
  - allow hidden contribution to uneqaully amount to predict


  Background Problem of Transfomers -> parallezability
  
  - we cannot stack more layer because of sequentila behavior RNNs    
  - How to make thing paralleization ?  
      L shuod be able all word at once 

      1) keep seq inforamtion without the model being sequential
      2) seq2seq decode
          L everything 

 Transfomers 
---
 
  - attention 

     a -> b
     b -> a 

    we cannot assume that their attention is not them same 
    but it might be equal


  - which word come fist which word come next  ?
     
    * why they dont concatenate ? 

       concatenate :  good thing ->  the number wont be diluted
                      bad thing -> bad thing is no interaction 
                assumption : it would be too much to take concatenate because if seq is longer it might take more computation  
    

  - author choose to plus  
    
    * need to carefully when we plus the value should not be loss
     - seq fixed 
     eg.  trainning set len -> 100 but test set len = 1000
          they will not understand 101 position 

    soln they just keep it between zero and one 

    * intilize matirx txd pass through linear layers and pass through activation function to figure it out  

    * How to get positional embedding ?   
      pos = 1,..,T
      i - index from zero to d 
      d- embedding dim
     
      always have unique vector  for each of position
      different dim different frequencies 

      related binary bit they altenated -1, 0, 1 
      pros: can extend to infinite len
      cons: Not learnable

      the in different position the word embedding would have different embedding

 multihead attention
---
  * Xhat -> make 3 copy of this guys
  * pass it through different linear transformation
  * they create different with Q, k, V  
       but more comlexity 
         L solving by dk = d/heads -> we change the weight shape -> dk
         L why they use 8 -> they emprical study
  * Mulihead -> concate because each of them are independent 
       L they muliply Wo because they want to learn some linear transformation

  * bachnorm vs layer norm
    
      * batch norm
         - across batch, each dim independtly
         - we do it in computer vision each of dim 
             in this task we have feature like contrast, brightness, edge, etc. those value is very mean
      * layer norm

         - across dim, each batch independently  
            norm each of the word layer norm
         - in NLP each word have unqiuque feature we if layer norm we will lose the feature of word 

         - in layer norm every word is so unique if we do layer norm some semantic would be loss

         - in each of the word the number in each dim is not so differ because they are related  to keep stability
         

         - if we norm across batch it doesn't make sense because each word so differrent 
            
            eg. the and cat are really different so we should normalize word T the only we should normalize is d 

   * the keys is not attention the keys is because we can keep on  stackign 



      
