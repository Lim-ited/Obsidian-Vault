1. Parallelized BP process
2. Optimizing sparsified detector model
3. We anticipate that other decoder families – for example BP+AC [16], BP+LSD [18], and BP+CB [17]
4. application of the BP+BP+OTF decoder to various code families, including colour codes, hypergraph product codes [6], and lifted product codes [7].
5. Hardware Verilog implementation of BP+BP+OSD


(1) Simplified post-processing methods, building upon or refining inversion-based or clustering approaches: e.g., localized statistics decoding [29], ordered Tanner forest decoding [30], closed branch decoding [31], ambiguity clustering [32]; 

(2) Heuristic methods for improving the MP decoding performance by modifying the decoding rules: e.g., guided decimation guessing [33], collaborative check removal [34], symmetrybreaking techniques [35], refined or memory BP [36, 37], MP decoders with past influence [38]; 

(3) Diversity or ensemble-decoding techniques, which combine multiple decoders to improve overall performance and mitigate individual decoder failures: e.g., automorphism ensemble decoding [39] or Relay-BP [40]. Some approaches span multiple categories, e.g., stabilizer inactivation [25], check-agnosia [27], or speculative decoding [41], which are simplified post-processing methods, where the postprocessing is based on ensemble MP-decoding.