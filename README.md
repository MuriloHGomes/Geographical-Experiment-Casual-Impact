# Geographical Experiment with Casual Impact library 

Geographical Experiments are also named as GeoX. To make the idea more concrete, suppose you are leading the digital marketing team for a travel agency chain that has recently become interested in increasing the number of followers on its social nwtworks in a particular city in order to promote sales of travel packages in that location. As the media team leader, answer the following questions:

  - How would you prepare the campaign with the city in question?
  - Once the campaign has been run for the planned time, aew the results reliable?
  - How would you ensure that the increase (or descrease) in adherence to the campaigns during the of the experiment was not due to chance?
  - How would you ensure that the number of followers after the test are caused by effect of the campaigns?

The use of geographical experiments is to seek solutions to such questions, while trying to ensure consistency in the results obtained. To be able to design more general experiments, we will identify the abstract concepts of the problem presented and then think of solutions to it, so that with the solutions developed we can use them in similar circunstances involving other clients and actions.

First step is define the necessary concepts:

  1. Impact: stratefic actin taken;
  2. Objective: what is expect to be observed as the influence of the action;
  3. Metric: quantity used to measure the influence of the action on the objective;
  4. Target: geographical region (city, metropolitan region, country, etc) where the action takes place;

Now, lets re-elaborate the problem presented.

## Problematising

We can rewrite the questions asked using the concepts above and generalise them:

  - According to the defined goal, what metric will be used to measure the influence of the achieved impact on the goal?
  - Did the impact happend as planned? Did it change during implementation? Did the collection of metrics remain consistent throughout the period?
  - Are the changes observed in the metrics really a consequence of the impact? Were the any changes outside the team's control that could have affected the results?

Regardless of the information represented by the metric, by observing its temporal behaviour we will find the relationship between a quantitative value and a unit of time. For example: number of sales in a period of 1 month. In this format, we call the data time series $S$ which is defined as the tuples $(t, x)$ and are defined as follows:

```math
S = \{  (t,x) \in \mathcal{T} \times \mathcal{X}: \mathcal{T} \text{ is time set  and } \mathcal{X} \text{ is the metric set} \} 
```

If the impact has the expected effect, there will be a visible change in the behaviour of the time series observed from the start of the experiment. But even if the behaviour before and after is visibly different, we need to explain this difference. Because any approach based on the reality of a dynamic system, such as non-linear digital marketing, relies on approximations that are statically established by the relationship between the explanatory variables and the response variable, the model, although accurate under ideal conditions, may fail or be inefficient in the presence of intervening factors.

Once these precautions have been taken, we can use the product [Casual Impact] (https://www.notion.so/075329e5573142e18289df09f2a2bc52?pvs=21) as a consistency analysis tool, because since the target is specific, we can take a region that is similar to the target but has not been impacted. This gives us an approximation of what could have happened to the target if it had not been hit. And using a statistical approach, we can determine whether or not the impact was statistically significant.

To carry out this approach, we first need to decide which of the similarity criteria we will use to select the best comparison region. As there are different ways of quantifying the idea of similarity between different types of data, the choice has to be made with the reality of the problem in mind. Therefore, in the case of similarity between time series, we will use the measures of similarity between time series. To learn more about the techniques used to measure similarity, see [Similarity Measures and Dimensionality Reduction Techniques for Time Series Data Mining](https://www.intechopen.com/chapters/39030). 


## Results

For the default p-value as $\alpha = 0.05$ and `prior.level.sd = 0.1`, which determines the standard deviation that will be used, as recommended when there are doubts about the stability of the data collection during the event, we have the following results: 

Cidade	| valor-p |	Casual Effect statistically significant? |	Increased value |
| --------- | ----------- | -------------- | -------------- |
Fortaleza	|0.07	|no	| +70.17%|
Belo Horizonte|	0.04|	yes	| +101.26% |
Curitiba|0.03	|yes|	+114.52% |
Recife|	0.02|	yes |	+116.86% |
Porto Alegre	|0.14	| no |	+40.86% |
Campinas|	0.06|	no |	+74.21% |






