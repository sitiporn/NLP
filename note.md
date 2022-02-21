ui ~ sentence i 
hi ~ BERT(ui) in our case using Roberta
  shape : (batch_size,sequence_len,embed_size) 
  hi is the output of model which is last hidden layers before classifier head in the model architecture

1yi=yj ~ we select only the sample that come from the same class to compute in each i and j

T ~ the number of pairs that come from the same classes

t ~ temperature value 

