# A predictive signature based on the Resting-state Pain susceptibility Network 

Welcome to website of the RPN-signature!

_This site is under construction._

## Abstract
Individual differences in pain percetheption are of key interest in both basic and clinical research as altered pain sensitivity is both a characteristic and a risk factor for many pain conditions. It is, however, unclear how individual susceptibility to pain is reflected in the pain-free resting-state activity and functional connectivity of the brain.
Here, we identified and validated a network pattern in the pain-free resting-state functional brain connectome that is predictive of interindividual differences in pain sensitivity and provides insights into the contribution of regional connectivity changes.
Our method allows assessing the individual susceptibility to pain without applying any painful stimulation, as might be valuable in patients where reliable behavioural pain reports cannot be obtained. Additionally, as a direct, non-invasive readout of the supraspinal neural contribution to pain sensitivity, it may have broad implications for translational research and the development of analgesic treatment strategies.

## The RPN-signature

The Resting-state Pain susceptibility Network signature consists of an fMRI image preprocessing pipeline and a linear combination of specific functional connectivity values. Its output is a single number: a predicted pain sensitivity score, to be interpreted on the scale of the QST-based (Quantitative Sensory Testing) pain sensitivity score. See the paper (under review) for details.

- The list of predictive functional connections is to be found [here](https://github.com/spisakt/PAINTeR/blob/master/res/predictive_connections.csv).
(Note that a sufficient predictive performance is expected only with our dedicated preprocessing pipeline, see below)

- The nodes of the predictive network (with nodal predictive strength) can be downloaded [here](https://github.com/spisakt/PAINTeR/blob/master/res/RPN_predictive_network_nodes.nii.gz). Note that this map is not predictive on it's own, just a spatial map of the RPN-nodes.

## Inputs

This "research product" allows making predictions on the individual's pain sensitivity based on their resting-state fMRI measutrements. To calculate the prediction, you need an additional input, the T1-weighted anatomical images.

The predictive model should be robust for variations in imaging sequences. Neverthless, we have the following suggestions (which shouldn't be hard to meet):

### In general:
- 3T field strength

### Anatomical image:
- high-resolution, "close-to-isovoxel" T1-weighted anatomical image, e.g. 1x1x1mm

### Functional image:
- 8-12 min long resting-state fMRI scan
- whole brain coverage (actually, a few millimeter can be missed from the ventral part of the cerebellum, see the RPN regional connectivity map for reference: [https://github.com/spisakt/PAINTeR/blob/master/res/RPN_predictive_network_nodes.nii.gz]
- TR around 2.5 sec (the model might be robust to this, though)
- interleaved slice order
- approximately 3mm voxel
- carefull fixation to prevent motion artifacts

## Usage with docker

*** Coming soon ***

## Running the source code

- Image preprocessing and network calculation is based on our PUMI (https://github.com/spisakt/PUMI) python module (see page for installation and dependencies).
- Run pipeline script for image preprocessing and network calculation: [https://github.com/spisakt/PAINTeR/blob/master/pipeline/pipeline_PAINTeR.py]
- Adjust (if neccessary) and run [https://github.com/spisakt/PAINTeR/blob/master/scripts/run_all.sh to perform the prediction].
For a more detailed instruction, please contact Tamas Spisak (spisak.tms@uk-essen.de)

## Authors
Tamas Spisak<sup>1</sup>, Balint Kincses<sup>2</sup>, Frederik Schlitt<sup>1</sup>, Matthias Zunhammer<sup>1</sup>, Tobias Schmidt-Wilcke<sup>2</sup>, Zsigmond Tamas Kincses<sup>2</sup>, Ulrike Bingel<sup>1</sup>

1.	Department of Neurology, University Hospital Essen, Essen, Germany
2.	Faculty of Medicine, Ruhr-University Bochum, Bochum, Germany
3.	Department of Neurology, University of Szeged, Szeged, Hungary
