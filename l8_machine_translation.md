# Machine Translation

 NLP tasks      Attention
---

sentiment ana -> constiuency parsing tree rnn

Language Modeling -> RNN 
                  -> LSTM
                  -> LSTM + attention 
Machine Translation -> RNN + attention
                       seq2seq


 Pre-Neural Machine Translation
---

 x(German) -> y(English) 

 we count what ? 

 arg_y P(Y|x) -> arg_y  P(x|y)P(Y) ; ignore P(x)

 pararell -> equal pair of corpus language


  statiscal way : count -> count what ?
  neural : dot product ! 

 *table of aligment(we manually define)

  - one to one (morgan -> tom) 
  - one to many (flige -> will fly) 
  - many to one 
  - many to many
 

  * statiscal (everything done manually)
  
  - input -> feature enginering -> svm  
      * we can hand craft

  * nn ways

    - input -> black block -> output 
    
 Decoding for SMT
---
  * we do it inference mode    

Nerual machine translation 



 Greedy decoding 
---
 
 * takiing highest prob word like arg max would get wrong if the first one predict wrong then all other word in sentence get wrong -> suck 
 * we should explore path like DFS  then they invented Beam search

 Beam search
---
 
 - if Beam size k = 2 (numbers of parellel seach)
     if k=1 it's just simply greedy 
 -  blue numbers = score(y1,..yt) = 
 - no. of required hypo  = n =3 
 - they choose two high prob
 - we can many type of stoping crieteria 

- why do we need to involve RNN   
   - it's matter at what you want 
- how video to text would work ? 
- longer sentence 
   beam seach always choose shorttest sentence
     we can solve this problem by divide the score by seq len



h0 -> RNN                   -> ht -> RNN
 
   f1       f2    f3      f4    teacher forcing 
  
   cnn      cnn   cnn    cnn

  frame1  frame2 frame3 frame4
   


 - end-to-end everything at same time (very automatics)   

 Greedy decoding 
---
 * Testing 
 * inference
 * decoding

 problem is that if fist high prob wrong all of the rest become wrong 

 * can we do something depth first search

How do we evaluate MT ? 
  * by overlapping words
  BLUE-1 -> one word overlapping between predicted sentence and target sentence 
  BLUE -1 + BLUE-N / N 



ROUGE -> one score per gram


 NMT with attention 
---

 * using only final state very risky 
 * s1 come from h4
 * yhat_1 = f(Ws1 + b)
   
   s1 = f(<start>,h4)

   h4 may not contain all information

   we can do it another 
      
      we can doted
        S1 @ h1 , S1 @ h2...,S1 @ hn 
        
        h1,h2,s1 is the subset of Rh -> so dot product try to find sim  

 * if we only use atteiont seq lose         
 * we assume that all of this h1,h2,h3, belong to Rh -> if dim not equal dot with some  W

 list e = [S1 @ h1 , S1 @ h2,...,S1 @ hn]
 softmax(e) -> then we dot with all h and add all them up -> Ct 

 ct= r1 + r2+...,rn : ct ~ context vector
 
 * r1 = h1 @ softmax(e1) : so the hidden size should be the same 
    * if shape not equal multiply with some W first 
 
 * we dont multply we dot prodcut and then them up -> ct  

 * yat_1 = f(W[C1;S1])
    change e -> variant of atteion happen

 Attention - fomally
---
 
  



        

