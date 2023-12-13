---
title: Scaling differences across 3T and 7T Scanners at UMinn, WashU, Mt. Sinai
created: '2015-01-15T11:15:24.037Z'
updated: '2015-01-15T11:21:39.019Z'
updated_by: Jennifer Elam
source: 
  https://wiki.humanconnectome.org/display/PublicData/Scaling+differences+across+3T+and+7T+Scanners+at+UMinn%2C+WashU%2C+Mt.+Sinai
space: PublicData

---
All 3T scanners tested (Siemens Skyra, Prisma, Trio?) are within 1% of a "ground truth" CT scan.

UMinn 7T is ~2.5% "smaller" than the "ground truth" CT scan.

Mt. Sinai School of Medicine (MSSM) 7T is ~2.5% "smaller" than the "ground truth" CT scan.

Phantom results on the 3T Trios at WU and UMinn are similar and show close to veridical scaling.  For the main HCP 3T (Skyra) data, the scaling is reasonable though not perfect (after gradient nonlinearity correction); the residual corrections should be posted on the wiki but don’t warrant further action.   

For the Prisma, the correction factor is a bit larger.  One option is to incorporate a correction factor into the Prisma Lifespan pipeline (preferably as a separate step right after gradient nonlinearity correction).   

