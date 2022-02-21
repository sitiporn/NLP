# Chapter4: Dependecies parsing 

 CFG
---

 - the whole thing -> lexicon 
 - on right hand sidde call terminal

 - using cfg -> give tree 

 Dependecies parsing
---
 
 - some word is depend on antoher word 

 Dependecies as tree 
---
 - acyclic, single-root how the power algorithm come when they are cyclic and and single root   

 * why we need dependencies parsing ?  
     * coreference resolution -> require understandign dependencies parsing  

  Dependecies Treebank
---
  * the Pen tree bank is one of the best ground truth 

  how do we build a parser
---
  - we should have some constraint  
     * vertex has exacyly one incoming arc

  Projectivity
---

    * it cross the word 
       * NN cannot solve this problem

 Greedy thransition-based parsing 
---
  * stack -> box 
  * beffer the guys who eat the word 
  
  * root depends on the most powerful or representative because just look at the depends of the root we can understand what is the sentence is about 

 MaltParser
---
* use transition as algorithm for right decesion we use nn 
* classifier woul be predict shif left right 
  
  if consider relationship  
      classifier more thing -> magnitude of relationship    
          |R| x 2 (left,rihgt) + 1 (shift) 

* we got stack, buffer a what do we feed into the nn ?   

* MaltParser  
    they feed feature as one hot encoding vector
    v = 5000 
    + mean longer  

 buffer:[0,..,1]  +  whatever what words are on to the top buffer  
    len = 5000  what        what is currently inside stack
      

 * futher exaple to two ways beam search  
        * after that compare loss with tree bank

 Evaluation Parser 
---
   * unlabeled score just check dependencies (UAS)
   * label score look both relation and  dependencies (LAS)

 A Neral transition-based 

 X = [e;vpos;label] 
 e = embeddings <- change from feature vector is big as too big 

 * they still use transition based 
 * sent/s : amount of word that they can consume

 A neural graph-based dependency
---
 * can handle non-projective 
 * if ground truth is non-projective would be trouble  
      * but Pen tree bank  non-projective or at least fix non-projective manually 
 * other dataset would be non-projective(corss dependencies)
 
    * cannot use transition based  non-projective

 idea
 * best incoming arc
 * minimum spanning trees
 
 eg. I ate food 
      * cut down arrow and each of word incoming arrow
      
      transition based -> speed , cannot work with non-projective 
      graph based -> accuracy, can work with non-projective but really slow 
 
 * common way other dataset that is not Pen Tree bank
     * use-transional based but fix all non-projective


 Word vector evaluation
---
 intrinsic metrics 
      * try to evaluate itself or anologus
     eg. similaries
      * how well capture sematic(meaing) and syntatic(grammar)
        
        a is to b as is to 

 extrinsic 
     * is it increase evaluation acc

 different type of task have different method of way of measure similaries  (eg. grammar, meaning)
