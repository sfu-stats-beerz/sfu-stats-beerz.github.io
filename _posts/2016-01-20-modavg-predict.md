---
title:  Predicting responses with model averaged coefficients
author: Amanda Kissel
---

Here's some code from [Rylee Murray](https://twitter.com/ryleega) for predicting responses with model averaged coefficients. In this particular example, he uses the models that sum to 95% of the cumulative AIC weight. But note that the models you average will depend on your question and specific analysis. 

{% highlight R %}
#using 
library(AICcmodavg)
#make a list of the model names and models to be put into AIC selection
modlist<- fitList('mod1'=mod1, 'mod2'=mod2, 'mod3'=mod3)

#create an AIC table
AICtable<- modSel(modlist)

#pretend AIC table
model<- c('mod2', 'mod1', 'mod3')
delta.aic<- c(0, 1.5, 8)
cum.weight<- c(0, 0.95, 1)
table<- data.frame(model, delta.aic, cum.weight)
table

#make a new list of the models within 0.95 cum.weight by hand (there are other rules of thumb for picking which models to average)
modlist.95<- fitList('mod2'=mod2, 'mod1'=mod1)
#or do it automatically
modlist.95<- get.models(AICtable, cumsum(weight)<= .95)

#use the models within 0.95 cumulative weight to make a model averaged prediction
modavgPred(modlist.95, newdata=some.new.data)

#using
library(MuMIn)
#make a global model and then run all possible combinations
global<- lm(response~a+b+c, data=data)
models<- dredge(global, evaluate=T) #evaluate=T tells dredge to run all possible combinations and evaluate them based on AIC, if evaluate=F then it will print a list of models with all possible combinations of variables

#get models within 0.95 cumulative weight
models.95<- get.models(models, cumsum(weight)<= .95)
#conduct model averaging with models up to 0.95 cumulative weight
modavg<- model.avg(models.95)

#make model averaged predictions
predict(modavg, newdata=newdata)"
{% endhighlight %}
