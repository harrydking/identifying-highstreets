# Identifying high streets in Yorkshire
Identifying high streets in Yorkshire using DBSCAN clustering

# Background
Traditionally, high streets played an important role as community centres, where people of all ages mixed (Housing Communities and Local Government Committee, 2019). However, in recent years, the growth of online shopping has had an impact on both city centre retail and the high street (Nanda et al., 2021). Footfall has declined, and vacant shops are a common sight. COVID-19 has accelerated these pre-pandemic trends and may lead to further high street changes (Nanda et al., 2021).

To successfully track the changes occurring on the high street, it is important to define what actually constitutes a high street. Whilst there is no catch-all definition of a high street, the ONS suggests that it is a “named street predominantly consisting of retailing, defined by a cluster of 15 or more retail addresses within 150 metres” (ONS, 2019). The main piece of research attempting to identify high streets in Britain was conducted by the Ministry of Housing, Communities and Local Government in collaboration with the ONS and Ordnance Survey. Whilst this map effectively shows the locations of high streets in Britain, the underlying data used is not publicly available and only shared with local government. Therefore, our challenge was to create a high street map that could be shared openly with the public. We approached this by searching for all clusters of commercial retail properties within Yorkshire. We decided to investigative the whole of Yorkshire as we wanted to ensure our technique worked across both urban and rural areas, whilst not using data for the entire country kept the computational requirements manageable on our personal laptops. For this project, we opted to use the ONS definition of a high street.

# Method
To identify high streets, we used a subset of the OS AddressBase Plus dataset, focused on an area of Yorkshire around Leeds and York. Whilst this dataset is not open source, it did give us the opportunity to develop a technique to identify high streets that could theoretically be applied to a similar public dataset. The AddressBase Plus data contains a number of pieces of information about each property in Britain. Most usefully for our study, this includes the property classification, x and y coordinates, local authority organisation, town name and street description/name.

Having only retained the variables required for the study, we filtered the dataset further, only keeping properties that were classed as “CR” (Commercial Retail) by the Ordnance Survey. We then filtered further, removing properties in towns/cities that did not have more than 15 commercial retail locations. This was followed by a final round of filtering in which properties were removed were on streets with less than 15 total commercial retail addresses. Finally we used DBSCAN clustering, that groups densely grouped data points together, to identify the high streets within the study area.

# Results
Our process successfully identified high streets in Yorkshire. As mentioned previously, understanding what a high street is, and where it is located is very important for observing the changes occurring and to mitigate the impact of modern technology. This map could help decision makers quickly identify the locations of high streets. We undertook some testing using Google Street View, and found that high streets defined by our clustering generally corresponded to real world high streets.

# Opportunities for future work
However, there are still numerous opportunities for further work. Firstly, there are a few issues with the method applied in this study. Taking the ONS definition does eliminate many smaller rows of shops that locals may consider high streets (and be threatened by similar risks). Secondly, our clustering picked up areas like town centres where there is a high concentration of commercial retail, but not actually high streets. Furthermore, we did not have the time to overlay the road network onto the map, which could have allowed us to identify actual streets rather than just clusters of commercial retail properties.

# Reference List
Housing Communities and Local Government Committee. 2019. High streets and town centres in 2030.

Nanda, A., Xu, Y. and Zhang, F. 2021. How would the COVID-19 pandemic reshape retail real estate and high streets through acceleration of E-commerce and digitalization? Journal of Urban Management. 10(2), pp.110-124.

ONS. 2019. High streets in Great Britain. [Online]. [Accessed 10 February 2022]. Available from: https://www.ons.gov.uk/peoplepopulationandcommunity/populationandmigration/populationestimates/articles/highstreetsingreatbritain/2019-06-06
