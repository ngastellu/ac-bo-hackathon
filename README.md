In collaboration with Ben Weiser, Sylvester Zhang, and Jérôme Genzling.

We want to optimize a protein to achieve better binding affinity to a certain substrate. This can have applications to biologics such as antibody therapeutics, enzymology, and in the case of this project, biosensors. We aimed to use Bayesian optimization to mutate the residues of a protein to achieve better binding affinity to fentanyl. This can be used for drug testing to detect fentanyl at higher sensitivities. 
Our methodology, was to use a pre-train a BERT language model trained to predict binding of ligands to a given protein from a sequence publish by Andrew E Blanchard. We give the amino acid sequence of the protein and the smiles string of fentanyl to this model and it outputs score related to binding affinity. We then use Bayesian optimization to query position and amino acid to mutate to and subsequently predict the next best position and amino acid to try next. 
We want to start with a protein that already has affinity to fentanyl so we took a previously developed protein published by Lisa M. Eubanks. We analyzed the protein and selected the residues with 5 angstroms of the ligand to be selected for possible sites of mutagenesis. Then take a mutation if we find it increased the binding above a certain threshold, and do this until we find 3 mutations chosen by BO which our language model predicts to have high binding affinity. 
We compared the methodology to a baseline of using random mutations. And we look at using other acquisition functions. We then took our results and analyzed them using pymol’s mutagenesis tool which showed how the suggested changes could lead to new interactions being formed, and how some lead to clashes potentially changing the conformation of the protein. Finally, we investigated the changes of these mutations on the structure using alpha fold. 

Starting protein found here: https://www.rcsb.org/structure/5TZO (Paper:  https://doi.org/10.7554/eLife.28909)
Binding affinity model we used: https://github.com/ORNL/affinity_pred/tree/master  (Paper: https://doi.org/10.1177/10943420221121804)

Thanks for checking our project out!
