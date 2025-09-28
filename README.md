1) Original COLBERT Scoring Function (MaxSim) :

   $Q = {E_{q_1}, E_{q_2}, E_{q_3} .\cdots, E_{q_N}}$ be the set of N token embeddings for a query

   $D = {E_{q_1}, E_{q_2}, E_{q_3} .\cdots, E_{q_M}}$ be the set of M token embeddings for a document.

   The original COLBERT Score s(q,d) is the sum of the maximum similarity for each query embedding:

   $s(q,d) = \sum_{i=1}^{N} max_{j=1}^{M} (E_{q_i} E_{d_j}^T)$.

    <div align="center">
      <img src="https://github.com/user-attachments/assets/b1e78042-8548-4eb3-840f-a9acbcff020d" width="600" height="400" alt="image" />
    </div>
   Adapted from "ColBERT- A Complete Guide" by V. Singh, 2024, Medium. Retrieved from https://medium.com/@varun030403/colbert-a-complete-guide-1552468335ae*




3) Modified COLBERT Scoring Function:
   So there will be two new inputs which are sets of scalar importance weights for the query and document embeddings, respectively.

   $Q_i = {i_{q_1}, i_{q_2}, .\cdots, i_{q_n}}$

   $D_i = {i_{d_1}, i_{d_2}, .\cdots, i_{d_m}}$

   $s_{modified}(q,d) = \sum_{i=1}^{N} i_{q_i} * i_{d_{j^*(i)}}(max_{j=1}^{M} ( E_{q_i} E_{d_{j}}^T))$

   where the index of the best matching document token, $j^*(i)$

   $j^*(i) = \arg\max_{j \in \{1, \dots, M\}} \big( E_{q_i}^T E_{d_j} \big)$

   <div align="center">
     <img src="https://github.com/user-attachments/assets/2d65fb33-b16f-4311-8e64-869962f95460" alt="Modified ColBERT Diagram" width="750" height="500" />
   </div>




