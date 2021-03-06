# Restart-problem-of-MarsWRF-model
Dear developing members and the users of MarsWRF model,  

We’ve found a problem in restart runs. The results are divergent between the original continuous integration and the restart runs, especially when there is a global dust storm. But the results are “bit identical” if the same restart file is used. It implies that the integration of the model should be ok, but some variables may have been missed in the restart file. (see the .jpg file)  

Then we’ve compared the wrfrst_ files between the original and the restart runs at every 6 min (time step is 2 min, bldt = 0, cudt = 0, radt = 30). At the initial time (at day 1, 12:00), the two files are “bit identical” (see the .txt file), but the biases have been presented at the second output time (6 min later). The results (see the .pdf file) show that the most significant relative biases (%) occur mainly in variables related to PBL parameterization process (e.g., coupled Q_c and Q_v tendency due to PBL parameterization at the surface) and the water/ice content (e.g., column integrated ice abundance at the surface). As suggested by Mark and Claire, we are now updating the ‘dev’ branch and testing the restart run with a smaller dump out interval and then fewer physical processes.   

Since the sensitive experiments are reliable based on the repeatability of the model, we sincerely look forward to any suggestion.
