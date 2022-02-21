# Constituency parsing 
  
  consider path or phrase not care relation like dependency grammar ? 
  
  eg. grammar check -> Constituency
      context -> dependency grammar 

  what is sematic composition ? 

  Language in recursive structure
---
  Why more the recursive the more ambugity

  version 1: Tree + RNN

  I don't like this movie  

 Discussion 
---
 
 * version 1:
    
    -using single W -> it could not capture high order complex sentences

    eg. det + noun    w: [low , high]
    eg  np + cc  w: [high,low]

    this cannot acheive by just one single Weight matrix 

    - No interaction between input words 
       
       [C1;C2] 
       eg. very good -> very amplifly good 
           (should have been) good -> (reverse activation)and negate "good" to be bad 
             in this case should have been negate good to be bad

  * version 2: Multiple W  + Tree + RNN

     - can capture different composition 
       eg. NP -> N + VP  : W1 
           NP ->  adj n  : W2
     
     - idea : simplify assing a different Weight matrix for diffrent composition 
     - Problem : speed
     - Soln : calculate Score likely combinaiton and some share likely to be the similar combination 

     - they still concatenation no interaction btw two word or two phrase 


   Question 
     
     Is is possible dont multiply with many W but stiil capture interaction between words  
     and also to allow different ways of interaction  

     activation mean that information in that area are important or contribute more to loss  

  Version 3: Matrix-Vector + Tree + RNN 
  
  * each of word 
     1) vector a, b
          * hold the meaning  
     2) Matrix A, B 
          * hold the interaction with possible neighbor word 

       [Ba Ab] -> [a b] 
      
    we get p how about P  
    P = wm @ [A;B] no need multiple W for composition  

    extra matrix per word 
    

    * experiment they can reverse things that look like negative word(not annoying) to positive which is true    
    nn can just remerber them (eg. lover great impressed marvelous)
    But !!! 
    * Problem 
       if we simply give wrong documents
        some time if the nn cannot model interaction very well it would be wrong  
         
         eg. the movie should have been better and more entertainnig -> positive which is wrong -> should be neg sentene
                    L if model is not super smart 

            1d CNN -> good at sentiment analysis because they get interaction of sentences 
               L keep on covulute  set of words
    
    version 4: Tensor + Tree + RNN      
         
         * Tensor 3D > more matirx

         
         * negated negative sentences change in activation only RNTN  
         * also Negated Positive sentene can be the higherst minus in RNTN 
    
         takeaways
          * no limitation in this work 
          * sentiment or sentence classificaiotn is really hard onece we make it very short sentence
          * Nowdays, not many work uitilzed such tree-based appraoch 
                * tree structure are not allow to work on GPU 
                * CNN -> can capture bigram trigram
                * attention -> capture all possible combination 

          * such tree-based work well on language structure not natural language 
          "No one use any more but can learn their philosophy how reserch think 

                 



    

