How to use can refer to:
D:

cd C:\PEPred_Suite
java -jar PEPred_Suite.jar example.txt Type Confi
（java -jar PEPred_Suite.jar example.txt ACP 0.5）

help:
The PEP_data.zip file needs to be decompressed before running the forecasting function.
example.txt is the input sequence data, TypType has 10 options {AAP, ABP, ACP, AVP, AIP, CPP, QSP, SBP, ALL, OP};
Confi is the confidence setting, the default is 0.5, the user can define, the range is 0~1 (do not need to be set when the type is OP);
Among them, {AAP, ABP, ACP, AVP, AIP, CPP, QSP, SBP} correspond to the eight peptides in the paper respectively, and the user can select the corresponding type to predict the sequence;
When the Type selects "All", the program can simultaneously predict 8 peptides.
When the Type selects "OP", the user will use the method of our feature selection to training the data set and derive the optimal features.


note:
1.The input file format requires the fasta format:
>P_1
ARPAKAAATQKKVERKAPDA
>N_1
TVEIVMGLEEEFQISVE
The positive case label defaults to 0, and the negative case label defaults to 1; or the label can be defined by the symbol "|".
>P_1|1
ARPAKAAATQKKVERKAPDA
>N_1|0
TVEIVMGLEEEFQISVE
2.The space character cannot appear in the specified cd path.
3.The input sequence should not be less than 10, and each sequence should be longer than 5.
4.Need to be in the windows operating system, and install the java 1.8.0_144 environment.

Then the result is as follows:
1.We display the results of the best features in the Optimal_feature.csv file and provide complete results of the relevant functions obtained by the SFS method in the Result_FT.csv file, allowing the user to select the best features.
(The related feature descriptors obtained using the SFS method are located in its subfolder / New_feature / FT_arff)
2.There are 99 independent feature descriptors in the base feature pool in the arff_out folder.
3.In the New_feature file, there is the mrmR score file FT.mrmrout and the feature extraction first step file FTC.arff.

references:
Leyi Wei, Chen Zhou, Ran Su, Quan Zou. PEPred-Suite: improved and robust prediction of therapeutic peptides using adaptive feature representation learning.Bioinformatics. 2019. (SCI, JCR-2, IF2017=5.4). DOI: 10.1093/bioinformatics/btz246.
