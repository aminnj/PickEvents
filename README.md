Syntax is ```edmPickEvents.py [DATASET] [EVENTSFILE]```.
The events file ("ECALHoles_DR010.txt" in this case) must be of the form:

run:lumi:event

run:lumi:event

...

Setup:
```
cmsrel CMSSW_7_4_1_patch4
cd CMSSW_7_4_1_patch4/src
cmsenv
git clone https://github.com/aminnj/PickEvents.git
mv PickEvents/PhysicsTools .
mv PickEvents/ECALHoles_DR010.txt .
rm -rf PickEvents
scram b -j 10
cmsenv
source /cvmfs/cms.cern.ch/crab3/crab.sh
edmPickEvents.py  "/MET/Run2015A-PromptReco-v1/RECO" ECALHoles_DR010.txt --crab
crab submit -c pickevents_crab.py
```
