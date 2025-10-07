# Pedestrian Level of Service (PLOS) in Saskatoon


## Introduction 

Improving pedestrian infrastructure has become a growing priority in urban populations, supporting walking as a practical and appealing mode of transportation. Cities are increasingly designing streets in ways that promote active mobility and prioritize accessibility, incorporating features such as sidewalks, crosswalks, and bicycle lanes (Raad & Burke, n.d.). There has also been growing interest in evaluating how public spaces serve pedestrians – not only in terms of function, but also in terms of safety and comfort (Raad & Burke, 2018). 

One of the most widely used metrics for assessing the overall quality of the walking environment is Pedestrian Level of Service (PLOS) (Landis et al., 2001). This metric incorporates a broad range of variables, including both quantitative and qualitative elements, aiming to determine whether a given area provides suitable conditions for walking, particularly in terms of comfort and safety (Kadali & Vedagiri, 2016; Raad & Burke, 2018).  


## Literature Review 

### Core Components of Pedestrian Level Of Service 

PLOS can be calculated in various ways depending on the purpose of the evaluation and the data available, but several key components emerge consistently across the literature, integrating a combination of physical, environmental, and traffic-related factors. Commonly mentioned variables include sidewalk width, buffer zones, surface quality, pedestrian flow, traffic volume, and presence of obstructions (Kadali & Vedagiri, 2016; Nag et al., 2020; Raad & Burke, 2018). These characteristics often vary within cities, with inner-city areas generally exhibiting higher walkability, while suburbs and peripheral zones tend to score lower (Conderino et al., 2021). Yet, many existing PLOS models emphasize broad infrastructure categories and often overlook the heterogeneity of pedestrian environments within cities (Conderino et al., 2021; Nag et al., 2020). 

In 2020, Nag et al. synthesized the PLOS literature into three central constructs: infrastructure, perceived safety, and network connectivity, arguing that these dimensions are deeply interconnected, and that effective PLOS assessment requires a balance between micro-scale design elements (e.g., surface material, lighting) and broader spatial considerations, like the continuity and directness of sidewalk networks. 

### Approaches to Measuring PLOS 

Building on the key components, researchers have employed diverse methodologies to capture pedestrian experience, which have evolved along with the priorities of PLOS research. Some studies apply statistical models to analyze perception data (Kang et al., 2013), while other use index-based scoring systems to evaluate infrastructure and user experiences (Ahmed et al., 2021). For example, Ahmed et al. developed a scoring framework for pedestrian crossings using 17 indicators, weighted by their perceived importance. Similarly, Rahul and Manoj (Rahul & Manoj, 2020) used latent-class modeling to demonstrate that pedestrians form subgroups that weigh convenience and safety differently.  

The diversity in methodological approaches suggests a shift from infrastructure-based evaluations toward more user-centered frameworks centered on context. Thus, adaptable frameworks capable of capturing design elements and their spatial distribution are needed.  

### Limitations and Opportunities for Advancement 

While PLOS is, in general, a widely accepted metric for evaluating walkability, several limitations have emerged regarding its practical implementation. Conventional models, evolving from level-of-service models created initially for motor vehicles, have often prioritized engineering standards, sometimes neglecting the broader pedestrian experience (Kang et al., 2013). Recent research (Kang et al., 2013; Rahul & Manoj, 2020) emphasizes that pedestrian preferences are not uniform, highlighting the importance of perceived safety, comfort, and context in shaping evaluations of walking environments. This supports the idea that subjective individual experiences are just as important as physical infrastructure in shaping walking behavior. Yet, some authors have pointed out that few studies have explored individual perception and social aspects of walking as a form of transportation (Nag et al., 2020; Rahul & Manoj, 2020). This gap is critical, as pedestrian behavior depends not only on the physical characteristics of infrastructure, but also on perceptions of safety, comfort, and overall environmental quality, highlighting the need for more adaptable, context-sensitive models.  

Taken together, the literature demonstrates that PLOS is a flexible, evolving framework. As urban areas continue to evolve towards a more walkable and sustainable future, models that integrate diverse variables, methodological innovation, and user perception, will be essential for guiding infrastructure improvements and ensuring equitable access to high-quality pedestrian environments.  

## Methods 

All calculations and data processing were conducted using R.  

To evaluate pedestrian infrastructure quality across Saskatoon, we developed a scoring framework based on three features of sidewalk and pathway segments: width, class (e.g., sidewalk, shared pathway, trail), and material (e.g. concrete, asphalt, gravel). Each segment was assigned a score for each feature using a predefined rubric reflecting its expected comfort level and accessibility for pedestrians. These three feature scores were then summed to calculate the quality score for each segment. 

Next, this score was weighted by segment length to account for the relative contribution of each segment within its corresponding Dissemination Area (DA). Weighted scores were summed for each DA and normalized by DA area (points/km2) to be able to compare between areas of different sizes. 

The resulting PLOS density values were classified into four categories: Low (<80), Medium (80-160), High (160-240), and Very High (>240 points/ km2). These categories were used to map the pedestrian infrastructure quality across Saskatoon, with each DA assigned a colour according to its classification. 

The pedestrian scores were then joined to DA polygons, which resulted in a map, where based on the PLOS classification, areas were categorized by colour to reflect the relative accessibility and quality of pedestrian infrastructure. 

Figure 1. Segment-level Pedestrian Level of Service (PLOS) in Saskatoon. 
[View Figure](https://github.com/walkabillylab/plos_saskatoon/blob/main/plos_final_code_segments_files/figure-html/unnamed-chunk-11-1.png)
[View Code](https://github.com/walkabillylab/plos_saskatoon/blob/main/plos_final_code_segments.Rmd)

Figure 2. Continuous Pedestrian Level of Service (PLOS) density in Saskatoon. 
[View Figure](https://github.com/walkabillylab/plos_saskatoon/blob/main/plos_final_code_files/figure-html/unnamed-chunk-15-1.png)
[View Code](https://github.com/walkabillylab/plos_saskatoon/blob/main/plos_final_code.Rmd)

## Results 

The PLOS map of pedestrian segments in Saskatoon reveals a clear variation between central and peripheral neighborhoods, reflecting differences in sidewalk quality, width, and surface material. 

High and Very High PLOS scores are concentrated in the city’s centre, particularly in Downtown, Nutana, Broadway and City Park. These areas exhibit higher-density environments with more established infrastructure, resulting in more continuous, comfortable, and accessible pedestrian routes. 

Medium PLOS scores are found in neighborhoods such as Rosewood, Willowgrove, and Kensington, which are newer areas right outside the denser central areas of the city that provide some pedestrian infrastructure but often have gaps in quality or connectivity. 

Low PLOS scores are most common in outer suburban and industrial areas, especially in larger, less dense dissemination areas like West Industrial, Montgomery Place, Sask Power Management Area, and Sutherland Industrial. These locations are characterized by newer development patterns with car-centered layouts and limited pedestrian-supportive features. 

Overall, the results evidence a clear centre-periphery divide in pedestrian infrastructure, with central neighborhoods offering more support for walking while suburban and industrial areas remain largely car-oriented. These findings underscore the need for targeted infrastructure in areas with lower PLOS to improve accessibility, safety, and equity in Saskatoon’s pedestrian network.  

## Validation with Walking Rate 

To further examine the relationship between pedestrian infrastructure quality and walking behavior, we examined an additional variable, walk rate, across dissemination areas (DAs) as a behavioral outcome to validate the PLOS score. Walk rate (or walk mode share) was sourced from the Statistics Canada 2021 Census of Population and represents the percentage of commuters whose primary mode of travel to work is walking.  

Higher walking rates are concentrated in Saskatoon’s central neighborhoods, overlapping with areas of higher PLOS. In contrast, suburban and industrial zones exhibit lower PLOS and lower walking mode shares.  

Figure 3. Walking Rates (%) by Dissemination Area, Saskatoon. 

[View Figure](https://github.com/walkabillylab/plos_saskatoon/blob/main/walk_rate_scatterplot_files/figure-html/unnamed-chunk-7-1.png)
[View Code](https://github.com/walkabillylab/plos_saskatoon/blob/main/walk_rate_scatterplot.Rmd)

The scatterplot shows a weak-to-moderate positive correlation: as PLOS scores increase, walking rate also tends to increase. This suggests that while high-quality pedestrian infrastructure is associated with more walking, other elements, such as land use and built environment factors, also play a critical role in creating walkable communities. 

Figure 4. Validation: PLOS Density vs Walking Rate, Saskatoon Dissemination Areas. 

[View Figure](https://github.com/walkabillylab/plos_saskatoon/blob/main/walk_rate_scatterplot_files/figure-html/unnamed-chunk-6-1.png)
[View Code](https://github.com/walkabillylab/plos_saskatoon/blob/main/walk_rate_scatterplot.Rmd)

## Conclusion and recommendations 

There are clear disparities in pedestrian infrastructure quality across Saskatoon. To promote equity and accessibility, infrastructure investments should focus on suburban and industrial areas with low PLOS scores. Improving sidewalk connectivity, width, and surface quality would help reduce inequalities in walkability, contributing to increased pedestrian activity and healthier, more active communities.  

## References 

Ahmed, T., Moeinaddini, M., Almoshaogeh, M., Arshad, J., Nawaz, I., & Alharbi, F. (2021). A New Pedestrian Crossing Level of Service (PCLOS) Method for Promoting Safe Pedestrian Crossing in Urban Areas. International Journal of Environmental Research and Public Health, 18(16), 8813. Public Health Database; Publicly Available Content Database. https://doi.org/10.3390/ijerph18168813 

Conderino, S. E., Feldman, J. M., Spoer, B., Gourevitch, M. N., & Thorpe, L. E. (2021). Social and Economic Differences in Neighborhood Walkability Across 500 U.S. Cities. American Journal of Preventive Medicine, 61(3), 394–401. https://doi.org/10.1016/j.amepre.2021.03.014 

Kadali, B. R., & Vedagiri, P. (2016). Review of Pedestrian Level of Service: Perspective in Developing Countries. Transportation Research Record, 2581(1), 37–47. https://doi.org/10.3141/2581-05 

Kang, L., Xiong, Y., & Mannering, F. L. (2013). Statistical analysis of pedestrian perceptions of sidewalk level of service in the presence of bicycles. Transportation Research Part A: Policy and Practice, 53, 10–21. https://doi.org/10.1016/j.tra.2013.05.002 

Landis, B. W., Vattikuti, V. R., Ottenberg, R. M., McLeod, D. S., & Guttenplan, M. (2001). Modeling the Roadside Walking Environment: Pedestrian Level of Service. Transportation Research Record, 1773(1), 82–88. https://doi.org/10.3141/1773-10 

Nag, D., Goswami, A. K., Gupta, A., & Sen, J. (2020). Assessing urban sidewalk networks based on three constructs: A synthesis of pedestrian level of service literature. Transport Reviews, 40(2), 204–240. https://doi.org/10.1080/01441647.2019.1703841 

Raad, N., & Burke, M. (n.d.). Pedestrian Levels-of-Service tools: Problems of conception, factor identification, measurement and usefulness. 

Raad, N., & Burke, M. I. (2018). What Are the Most Important Factors for Pedestrian Level-of-Service Estimation? A Systematic Review of the Literature. Transportation Research Record, 2672(35), 101–117. https://doi.org/10.1177/0361198118790623 

Rahul, T. M., & Manoj, M. (2020). Categorization of pedestrian level of service perceptions and accounting its response heterogeneity and latent correlation on travel decisions. Transportation Research Part A: Policy and Practice, 142, 40–55. https://doi.org/10.1016/j.tra.2020.10.011 

 