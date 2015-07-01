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
edmPickEvents.py  "/MET/Run2015A-PromptReco-v1/RECO" ECALHoles_DR010.txt
source /cvmfs/cms.cern.ch/crab3/crab.sh
crab submit -c pickevents_crab.py
```
