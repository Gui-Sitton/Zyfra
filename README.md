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
