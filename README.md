# Zyfra

Prepare a prototype of a machine learning model for Zyfra. The company develops efficiency solutions for heavy industry. The model should predict the amount of pure gold extracted from gold ore. You have the data on extraction and purification. The model will help optimize production and eliminate unprofitable parameters.

**Data description**

*Technological process*
* Rougher feed - raw material
* Rougher additions (or reagent additives) - flotation reagents: Xanthate, Sulphide, Depressant
* Xanthate - flotation promoter or activator
* Sulphate - sodium sulphide for this specific process
* Depressant - sodium silicate
* Rougher process - flotation
* Rougher tails - product residues
* Float banks - flotation unit
* Cleaner process - purification
* Rougher Au - raw gold concentrate
* Final Au - final gold concentrate

*Step parameters*
* air amount - volume of air - volume of air
* fluid levels
* feed size - fed particle size
* feed rate

**Characteristic naming**

Here's how you name the characteristics:
[stage].[parameter_type].[parameter_name]

Example: rougher.input.feed_ag


Possible values for [stage]:

* rougher - (Raw ore) flotation
* primary_cleaner - primary purification
* secondary_cleaner - secondary purification
* final - final characteristics

Possible values for [parameter_type]:

* input - raw material parameters
* output - product parameters
* state - parameters characterizing the current state of processing
* calculation - calculation characteristics

**CONCLUSION**
The aim of this project was to prepare a prototype of a model based on extraction and purification data that predicts the amount of pure gold recovered from gold ore. In carrying out this task, we first pre-processed the data; this involved checking for duplicates, scaling the data, filling in the NaNS and adding targets to the test data set. We then analyzed the data, examining the concentration of metals at various stages, visualizing the total concentration of all metals after the main processes, determining whether the distribution in the training and test datasets is similar and removing outliers. We then created functions to calculate the final sMAPE score from predictions and targets, and trained several regression models. We selected the model that provided the lowest sMAPE score and obtained the score for the test datasets using the optimal parameters identified. Finally, we compared the score with the score provided by a sanity "model".

* Although the sMAPE score of our best model was very good, approximately 6.28%, we needed to test this model against a sanity "model" to get an accurate idea of our model's performance. As you can see, the sMAPE score of our sanity "models" was 7.54%, which is more than 1% higher than our score using the test dataset. However, this score is also lower than that obtained on the training dataset. Perhaps the reason we had a lower sMAPE on the test dataset has to do with the way the samples were chosen for each set.

* Although our model was not able to provide an sMAPE score much lower than the sanity "model" score, we understand that it is in Zyfra's interest to adjust its process in order to obtain the maximum amount of gold from the ore. We therefore recommend that those who prepare the data and understand the gold extraction process carefully examine the features in the full data set and organize them by importance (perhaps by correlation with targets). Selecting only those with the highest importance, we recommend collecting more data and using it to train and test the regression models again. Perhaps, with weighted features, it will be possible to obtain a model that gives a much lower sMAPE score than the sanity "model".
