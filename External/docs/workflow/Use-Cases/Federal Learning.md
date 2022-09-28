# Federal Learning (FL)

Federated Learning allows participants to collaborate on model training or predictions without sharing local sensitive data. Although the data used in FL doesn't get to share with other participants, it is still vulnerable to local attacks, and can be safe-guarded with TEE. In addition, the information (such as median outputs, parameters) exchanges across participants also needs to be protected using either HE, MPC, or secure channels between TEE enclaves; preventing malicious participants from deducing valuable information from median outputs. 

Amber provides attestation for the participants in federal learning. Each participant can run inside a TEE and when they join the FL cluster, they get attested by Amber. The FL cluster can grant the participant join the cluster to use shared data only if the participant has a valid Amber attestation token.
Customer PoCs:
