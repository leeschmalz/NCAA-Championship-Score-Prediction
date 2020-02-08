# NCAA-Championship-Score-Prediction

In 2018 I participated in the fantasygrade.com pick 'em competition for the NCAA Wrestling Championships. To my delight, I won the competition against hundreds of other contestants and made $1000 as the grand prize. 

This year, 2020, I built a machine learning model based on a dataset provided to me by wrestlestat containing statistics from the 2019 season like Bonus Percentge, Win Percentage, Conference, Record, and much more, in combination with a dataset I built myself that scored the 2019 wrestling championships(found in my NCAA-Championships-Data Repository). I have not included the wrestlestat dataset here to uphold its propietary value to their company. For now, this model performs a train test split on the 2019 data and predicts a regression output of scores for the test data, and it performs pretty well (RMSE approx. .37-.5, depending on the random split, out of a ~3.8 unit span). Once the 2020 season ends and the NCAA Championship Brackets are set, I plan to use the 2019 data as a training dataset and predict on the 2020 dataset to predict the optimal fantasy team that maximizes points scored while remaining under the draft seeding cap.

Because the dataset from wrestlestat only contains data for ranked wrestlers, some of the participants in the NCAA tournament in 2019 were omitted, the unranked participants(average ~2-3 per weight class). This is likely not an issue for the model as the unranked wrestlers were in most cases not in contention for scoring significant points, regardless.

As seen by the scoring histogram, it is apparent that scores tend to follow a roughly exponential distribution. A logarithmic transformation was used to allow the data to be fitted by a linear regression prediction model.

To create the dataframe, the wrestlestat dataset had to be joined with the dataset I created. This was rather seamless other than the problem of joining on different name spellings of wrestlers. For example, my dataset used the name 'Cam Sykora' while the wrestlestat dataset used 'Cameron Sykora'. The fuzzywuzzy package came in handy here to ultimately join on names that were related by a fuzz ratio of 70/100 (with one weight class as an exception using a bit lower ratio).

I am excited to see how the model performs on the 2020 NCAA Championships competition, and will update here with my results following March 21, 2020.
