#TODO
DOSBox


1.	To retrieve the requirements from the HTML:


  `cd dosbox`
  
  
  `./grabHtml.py > requirements.txt`
  
  
  `./convertReqstoList.py > finalRequirements.txt` this produces a list of requirements  


2.	To extract function information:


  `cd ../srcML/bin`
  
  
  `./srcml ../../dosbox-code/src -o ../../dosbox/dosboxUnformatted.xml` this produces an xml file of all the source code


  `cd ../../stereocode-master`
  
  
  `./stereocode –i dosboxUnformatted.xml –f ../../dosbox/dosboxInfo.csv` this produces a csv file of function names, file locations, and line numbers


3. To create the call graph:

   `cd ../dosbox`
   
   
   `cp fileNames.txt cscope.files`
   
   
   `mv cscope.files cscope`
   
   
   `cd cscope`
   
   
   `cscope -b -c -R` this produces cscope.out
   
   
   `cd tceetree_1_0_1_sources`
   
   
   `./tceetree -i ../cscope.out` this produces tceetree.out which is a text call graph
   
   
   `dot -Tpng -O tceetree.out` this produces a png file to view the visual call graph
   
   
4. To calculate page rank of the call graph:
   
   
   `cd ../pagerank-master/cpp`
   
 
   `pagerank -d "->" ../../tceetree.out > pagerankScore.txt` this produces a list of page rank values for each function 





Inkscape


1.	To retrieve the requirements from the HTML:


  `cd inkscape`
  
  
  `./grabHtml.py > requirements.txt`
  
  
  `./convertReqstoList.py > finalRequirements.txt` this produces a list of requirements


2.	To extract function information:

  `cd ../srcML/bin`
  
  
  `./srcml ../../inkscape-0.92.0/src -o ../../inkscape/inkscapeUnformatted.xml` this produces an xml file of all the source code


  `cd ../../stereocode-master`
  
  
  `./stereocode –i inkscapeUnformatted.xml –f ../../inkscape/inkscapeInfo.csv` this produces a csv file of function names, file locations, and line numbers


3. To create the call graph:

   `cd ../inkscape`
   
   
   `cp fileNames.txt cscope.files`
   
   
   `mv cscope.files cscope`
   
   
   `cd cscope`
   
   
   `cscope -b -c -R` this produces cscope.out
   
   
   `cd tceetree_1_0_1_sources`
   
   
   `./tceetree -i ../cscope.out` this produces tceetree.out which is a text call graph
   
   
   `dot -Tpng -O tceetree.out` this produces a png file to view the visual call graph
   
   
4. To calculate page rank of the call graph: 
 
 
 `cd ../pagerank-master/cpp`
   
   
 `pagerank -d "->" ../../tceetree.out > pagerankScore.txt` this produces a list of page rank values for each function 
