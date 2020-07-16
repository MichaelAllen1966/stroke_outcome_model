# stroke_outcome_algorithm


Algorithm to calculate probability of a good outcome given thrombolysis or thrombectomy.

[![DOI](https://zenodo.org/badge/280125439.svg)](https://zenodo.org/badge/latestdoi/280125439)


## Run on BinderHub:

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/MichaelAllen1966/stroke_outcome_algorithm/master)


## Set up environment locally

To get the correct libraries and versions it is recommended that the provided conda environment is used. To create and activate the `stroke_outcome` environment used:

To create environment. Navigate to the `binder` folder.

`conda env create -f environment.yml`

To activate environment:

`conda activate stroke_outcome`

To deactivate:

`conda deactivate`

To update environment (from updated yml file):

`conda env update --prefix ./env --file environment.yml  --prune`

To remove the environemnt:

`conda env remove -n stroke_outcome`

## Inputs

All inputs take np arrays (for multiple groups of patients).

mimic: proportion of patients with stroke mimic

ich: proportion of patients with intracerebral haemorrhage (ICH). 
Or probability of a patient having an ICH, when using for a single patient.

nlvo: proportion of patients with non-large vessel occlusions (nLVO). 
Or probability of a patient having an NLVO, when using for a single patient.

lvo: proportion of patients with large vessel occlusions (LVO). 
Or probability of a patient having a LVO, when using for a single patient.

onset_to_needle: minutes from onset to thrombolysis

onset_to_ouncture: minutes from onset to thrombectomy

nlvo_eligible_for_treatment: proportion of patients with NLVO suitable for 
treatment with thrombolysis. Or probability of a patient with NVLO being 
eligible for treatment.

lvo_eligible_for_treatment: proportion of patients with LVO suitable for 
treatment with thrombolysis and/or thrombectomy. Or probability of a patient 
with LVO being eligible for treatment.

## Returns

Probability of good outcome: The probability of having a good outcome (modified
Rankin Scale 0-1) for the patient or group of patients (np array).

## References for decay of effect of thrombolysis and thrombectomy

Decay of effect of thrombolysis without image selection of patients taken from:
Emberson, Jonathan, Kennedy R. Lees, Patrick Lyden, Lisa Blackwell, 
Gregory Albers, Erich Bluhmki, Thomas Brott, et al (2014). “Effect of Treatment 
Delay, Age, and Stroke Severity on the Effects of Intravenous Thrombolysis with
Alteplase for Acute Ischaemic Stroke: A Meta-Analysis of Individual Patient
Data from Randomised Trials.” The Lancet 384: 1929–1935.
https://doi.org/10.1016/S0140-6736(14)60584-5.

* Time to no effect = 6.3hrs

Decay of effect of thrombectomy without image selection of patients taken from:
Fransen, Puck S. S., Olvert A. Berkhemer, Hester F. Lingsma, Debbie Beumer, 
Lucie A. van den Berg, Albert J. Yoo, Wouter J. Schonewille, et al. (2016)
“Time to Reperfusion and Treatment Effect for Acute Ischemic Stroke: A 
Randomized Clinical Trial.” JAMA Neurology 73: 190–96. 
https://doi.org/10.1001/jamaneurol.2015.3886.

* Time to no effect = 8hrs
