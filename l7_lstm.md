# LSTM

 Vanish Gradients
---
 * each of Gradient < 1
 * gradient would be small if we keep on multiplying  
    * the farther away you are from the higher tending of smaller gradient 
 
 * RNN better to learn sequential recency, and poor in syntatic recency


 * How to fix vanish gradients ? 
    
    - can try to preserve long termn relationship instead of fixing vanish gradients 
    - how about a RNN with a separate memory 
         - provide another alternate path for the grad to flow 
             to that h1 -> high chance vanishing
             multiple path h1 ->  not vanishing  
         - can memorize the word that far away and have some gradient involve 
            if have one path high change to create vanish gradient
         - can we create multiple path 
         -  
         

         the way that network can learn 
            1) back prob 
            2) rienfocement like get reward 

 Explode Gradients
---
  
 * if each gradient > 1  
 * result in inF or Nan 
 
 on that mountain we want some dim go pos and some dim go neg in each direction not so much about magnitude 

 
 let's   some gradient = 16

 scale_func(16) as much smaller  still kept the direction 

 * not much problem as vanish gradients

 * ghat -> there are many direciton  

     ghat / ||ghat|| -> unit vectors

 * 100 percent clip the grad -> good practice 

 LSTM
---
  * f(t) ~ what is kept and what to forget from previous cell state  
  * i(t) ~ to control part new cell contents are written to cell  
          * what shuold be written for each cell state
  * o(t) ~ control what part of cell to output 

  * c_prime_(t) ~ short term memory because it muliply with current input 
        * which actual information 
        * can be relu, LeakyRely, elu
  * c(t) ~  long term memory  
        * input gate can control  short term memmory from current state 
             input gate is a bunch of value between 0 and 1
        * forget gate choosing what we want from c(t-1)  
        * some may be take a little bit some may be take a lot 
        * Hadaman product because we apply the gate

  * h(t) ~ actual o/p 
       * we take c(t) which is actual information
       * elmemntwise with output gate
  * matrix is a bunch of value between [0,1]

  ** compare to RNN
     - they have one part to go 
     - the key grad to flow in Lstm

  * what is purpose outout gate 
     - just for flexibilty
     - proving antoher it help gradient to flow accroding to their experiments
     - just provide another set of weight 

 GRU
---
  * why we have three gates ? 
      there is no reason

  * no clear win between GRU and Lstm   
     - Lstm is very nice start point
     - GRU best efficiency


  *  Resnet coppying from LSTM
       - what is does it
           provide antoher path for gradient to flow
       - F(x) they dont need learn to much that why it might be identity


  * DenseNet
       - we can skip so many layer 

  * HighwayNet     

      - before skip they do some transformation 
      - mulpliy to some matrix 

  * the whole idead is 
     1) gradient to flow 
     2) identify function 

 Bidectionality LSTM
---
  *   as some time we have to get context from both direction  

  *   in RNN we dont do skip connection on we stack RNN

