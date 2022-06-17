data.rar file contains the Arabic KHATT and English IAM handwritten connected components written by 500 scribes per each dataset.
the files are already preproceesed and the connected component images are saved as a .MAT files. 

Raw datasets are fully accessible and freely available for reseraches purposes.
IAM Dataset can be easily downloaded from the following link:
	https://fki.tic.heia-fr.ch/databases/download-the-iam-handwriting-database

Khatt dataset is available and can be downloaded using this link:
	http://khatt.ideas2serve.net/KHATTDownload.php

-------------------------------------------------------------------------------------------
src.rar file contains the source code files used to implement the writer identification system.
The structure of source code files is as follows:

Writer_IdentiFication_System M script is used as the main module of the system. through this script, you can specify which target dataset, how many scribes are involved in the expirement, which feature you need to apply
*** Dependencies 
--> System_Main_Function M script, 

System_Main_Function M script was used to invoke the module of features extraction, invoke the module of generating the codebook, invoke the module of classification
*** Dependencies 
--> Build_Test_Train_Data_Sheet_1 M script, the description of this script is shown below.
--> Calculate_Occurrence_Histogram M script, was used to build a histogram for each reference and questioned document.
--> Calculate_Matrices_Similarities and Calculate_Performance M scripts were used in the classification process.
 
Build_Test_Train_Data_Sheet_1 M script was used to extract the features and save them as mat files for further processing. But before features extraction, this module is used to specify the most dominant points, extract batches
around the most dominant points, use these batches to build new textural blocks for the whole writer handwritten form. 
*** Dependencies here: 
--> Get_conn_com_tot_counts M script was used to retrieve the number of the available connected components per writer
--> dominantPoint M script was used to specify the dominant points with respect to high curvature
--> applyCollinearSuppression Mscript was used to reduce the number of dominant points of the connected component contour(remove redundant and noisy points)
--> Calculate_Block_Features M script was used to apply the underlying textural feature on the newly constructed textural block

efficientLBP M script, was used to extract the local binary patterns 

lpq_basic M script, was used to extract the local phase quantization 

ltp_image M script, was used to extract the local ternary patterns

HOG M script, was used to extract the histogram of gradiants
