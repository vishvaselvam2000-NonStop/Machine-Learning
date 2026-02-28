Its for Clasificaion problem , summarizes the metrics for each class in Multi - class / Binary Class problem.

Gives
* Precision
* Recall
* F-1 Score
* Accuracy


## 1. Precision:

              Precision  =           TP 
                              --------------
                                   TP + FP
             model posotive nu predict pana output la , ethana actual correct ?
             
         So To caculate  correct predicted positive, we first need total predcited  positive count , 
         , Total predicted positive = Model predicted positive + Model mistekenly predicted the negative as positive ( FP )
         so dinominator = TP + FP ( Total predicted positive)
         And nominator => we need here correctly positive data so on nominator we use TP

         So , Precision = TP / TP+FP . 
        So FP increase , Precision decrease , as its indirevtly proportional relation
        When FP will decrease and precision score increase? ,  when we decrease threshold (decision boundary) , only minute of samples classified as positive strict condition, 
        it includes the Samples near hard region will neglect , so False positive will be low , because it will classfiy samples which are very high chance as positive in safe region as positive.

        So ,  Threshold decrease => FP decrease => Precision increase , and vice versa.

        Threshold and False positive are directly proportional
        Precision and Fase positive are indirectly proportional.Hence precision and Threshold value are indirectly proportioanl.
        
         
            
  1. Is measure **" OF  samples predicted , how many were actually correct ? "**
  2. Focus: Predicted Positive for that class.
  3. High Precision: Model make few false positive error
 
     

  **Understand**
  1. Pre -- for prediction , just keep prediction as baseline , out of all predicted positives , how many are real positive / correct
  2. which tells predicted posotve ratio value , here precision is 1 then there is no falso positive, but if its less we have more fals positive
  3.  Precision proportional to 1/FP ( Precision increase , FP decrease and vice versa)

      
## 2. Recall:

              Recall =               TP
                              ---------------
                                   TP + FN

             Actual true samples la model ethana correct aa predict paniruku.

            So to calculate actual true smple , it is 
            Actual true = Model predicted True + Model mistakenly predicted true label as negative ( FN )
            hence its the base, its the denominator.
            We need to find rate model predicted postive in  actual true label , hence , model predicted positive in nominator

            nominator = TP
            Dinominator = TP + FN

            Recall / TPR = TP / TP + FN   ( Recall / Sensitivity / TPR )

            So FN increase , Recall decrease , as recall proportional to 1/FN.
            When Recall increase? , when we decrease  the Threshold value , vast number of samples predicted as positive, includes hard region
            samples are predicted as positive , even negative samples also predicted as positive, so False posotive will be increase
            very high , but leads to Vast number of samples predicted as positive , hecne False negative value will be less , So recall will be high.

            Threshold and False negative are directly proportional.
            Recall and  False negative are indirectly proportioanl. hence recall and threshold are indirectly proportioanl.

  1. Measure , **"OF all true positive sample , how many did model correctly predict"**
  2. Focurs: Actual positive for that class.
  3. High recall : Model misses few real positives.

## 3. F1 - Score:
                     
            F1 = 2.  Precision * Recall
                    --------------------
                      Precision + Recall

  1. Harmonic mean of the Precision and the Recall
  2. balance between the catching positve (recall) , and aviode false alarms (precision)
  3. Use when we need trade off between precision and the recall.

## 4. Accuracy:

            Accuracy =       TP + TN
                         --------------
                            TP+FP+FN+TN

  1. Simple fraction of the correct prediction
  2. Can be misleading for imbalanced classes / datasets.



