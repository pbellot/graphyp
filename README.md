# Graphyp Notebook

This notebook illustrates **Graphyp** for analyzing search sessions in collections of a digital library. It takes log files from Matomo as input and provides us with figures showing us the evolution of the Graphyp parameters along the search sessions and the routes of search by means of a bipartite graph. 

Matomo Log files must be previously filtered to eliminate connections from bots and requests for files other than papers. User IDs are associated to the requests to the Web server according to the anonymized IP address and sessions IDs are added based on the recorded timestamps. This means that we name a "session" a sequence of actions (content requests) performed by an anonymous user in a limited time. 

The process is then as follows. First, we divide all the logs into blocks of sessions. Then, for each session, within each block, we estimate the values of K as the number of articles read by a reader. This makes it possible to estimate, in each block, the number of readers N who have read K articles and thus the mean values of the different N and K for this block. α and β values as well as their ratio are calculated, for each block of sessions except the first one, from the mean values of N and K.

Once this is done, it remains to determine for each session its type according to the associated values of N, K and α/ β. Some thresholds make it possible to identify the tendencies towards the min/max values of N and K and towards ±infinity or stability (1) for α/β (for example, we can choose to consider K as type Kmax if K > Kmax – (Kmax – Kmin) x z with 0 < z < 1). Lastly, the sequence of types gives us the routes of search.

### Authors of Graphyp : 
- Renaud Fabre, Dionysian Economics Laboratory (LED), Université Paris 8, Saint-Denis, France
- Otmane Azeroual, German Center for Higher Education Research and Science Studies (DZHW), Berlin, Germany
- Patrice Bellot, Aix Marseille Université, CNRS (LIS), Marseille, France
- Joachim Schöpfel, Univ. Lille, ULR 4073 - GERiiCO - Groupe d’Études et de Recherche Interdisciplinaire en Information et Communication, 59000 Lille, France
- Daniel Egret, Université Paris Sciences & Lettres, 75006 Paris, France

### Reference:

Renaud Fabre, Otmane Azeroual, Patrice Bellot, Joachim Schöpfel, Daniel Egret. _A Scientific Knowledge Graph with Community Detection and Routes of Search. Testing "GRAPHYP" as a Toolkit for Resilient Upgrade of Scholarly Content._ 2021. ⟨hal-03365118⟩ https://hal.archives-ouvertes.fr/hal-03365118/document
