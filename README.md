```
cmsrel CMSSW_7_4_1_patch4
cd CMSSW_7_4_1_patch4/src
cmsenv
git clone git@github.com:ramankhurana/PickEvents.git
mv PickEvents/PhysicsTools .
mv PickEvents/ECALHoles_DR010.txt .
rm -rf PickEvents
scram b -j 10
cmsenv
edmPickEvents.py  "/MET/Run2015A-PromptReco-v1/RECO" ECALHoles_DR010.txt
crab submit -c pickevents_crab.py
```