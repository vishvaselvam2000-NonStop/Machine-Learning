# ROC Curve ( Reciever Operating characteristic Curve )

ROC Curve is grpaph that shows rate of True Positive Report (TPR) vs False Positive Report (FPR) for the 
all possible classification thrshold ( Tis means these vlue are acutal model predicted probablity value like 0.7 , 0.2 ).

## TPR (True Positive Report / Recall / Sensitivity ):

    TPR = TP / TP + FN

    Out of all active positive [TP (Model predicted postive + FN (Modle predicted postive as negative)] , how many model correctly detect postive.


## False Positive Report ( FPR) 

    FPR = FP / FP + TN

    Out of all negative , how many model wrongly classify as positive.

 ## NOW HOW ROC is constructed:
    1. If the mode lprediction for 5 inputs , then output probablity for each value will be
        (0.1, 0.3, 0.4, 0.5, 0.9) [ I round of the decimal one the probablity value ]

    2. Now ROC is drawing the graph of TPR vs FPR . but how we find models TPR and FPR rate , we can find that with model predicted probablities
    3. The model is predicted the probablity value , and based on our threshold value it will be result positive or negative  
    4. So for teh above five samples model give 5 predicted values , based on the model learning , now we will use threshold to make it as 0/1 if 
    threshold is 0.5 then p>0.5 = 1 or p< 0.5 = 0  

    5. So to plot Rate TPR vs FPR , we need True labels , and predicted lables
    6.  True labels , model actual output
    7. Predicted labels , modelpredicted output based on threshold  value
    8. But model only gives now probablities , with threshold we need to make prediction.
    9. So Instead of choosing one fixed number of threshold , we considering all possible theshold that model has predicted.
    10. So model predicted 0.1, 0.3, 0.4, 0.5, 0.9  instead of random threshold we taking . consdering model predicted probablities as the threshold
    11. So model consider all poosible model threshold
    12. that 0.9 - 0.3
    13. So first sort probablitie in descending order like  0.9, 0.5, 0.4, 0.3, 0.1
    14. Why we considering desceending as threshold value high FP rate will be less , thats the main goal 
    
    15. So we start with maximum threshold = infinity => predict all as 0 => TPR = 0 , FPR =0 , all value negative , hence point (TPR,FPR )=> is (0,0)
    16. Now next, 0.9  as threshold =>confuson matrix => compute TPR , FPR , plot (TPR , FPR ) aluesin graph
    17. Repeast this process for all threshold , until threshold = 0 , predict everything postive , hence TPR =1, FPR =1 s o plot final point is (1,1).

    THIS THE ROC Curve.

  ## WHAT ROC actual shows:
     How TPR increases when we allow more FPR. It visualize the trade off

  ## Final:
    IF ROC Curve plot is upper left most , then most of the positive sample predicted score is higher than negative score that is model able to predict
    correctly in all threshold , its not memorizing

    IF ROC Curve is closer to diognal , (1,1) , as ROC maximum point is 1,1 then the curve is slightly closer to digonal then that means , 
    TPR = 1, FPR =1 so its just randomly predicting. which is not ideal.

    IF ROC Curve is extended and close to right side lower then it predicting opposite that is probablity of negative number is higher than
    the positive number.



# AUC ( Area Under Curve) :

Area under ROC Curve.

AUC = P(positive score > negative score )

Probablity that models  ranks a positve haigher than the negative 

To find area between the Total ROC curve is by 

1. ROC  Curve is not smooth. , it is step shaped.
2. example , is (TPR,FPR) for two samples sample is (0,0)[threshold infinity], (0.2,0.6)[model predicted threshold], (0.5, 0.8)[model predicted threshold], (1,1)[threshold = 0]
3. We need to calculate area between two consecutive points
4. Formulae is using TrapeZoidal Rule ) =>
5.     Area of two consecutive points is (x1, y1) and (x2, y2) => (x2-x1) * (y1 + y2) / 2.
6. So we find area from 0 to first point => AUC1 , first point to second point => AUC2 , second to third => AUC3
7. So total AUC = AUC1 + AUC2 + AUC 3
8. This how AUC is calculated from the plotted points.
9. ITs the result  of total area of the ROC curve of 0 to 1 probablity , hece it always comes in 0 to 1
10.  if AUC = 1 , then model  have 100% higher probablity than lower probabloty , if its 0.5 its randomly calculating , if its lesser than 0.5
11.  then  it predicting inversly.
12.  
