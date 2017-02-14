#TODO
DOSBox


1.	To retrieve the requirements from the HTML:


  `cd dosbox`
  
  
  `./grabHtml.py > requirements.txt`
  
  
  `./convertReqstoList.py > finalRequirements.txt` this produces a list of requirements


2.	To extract function information:


  `cd stereocode-master`
  
  
  `./stereocode –i dosboxUnformatted.xml –f ../../dosbox/dosboxInfo.csv` this produces a csv file of function names, file location, and line number


3. To create the call graph:

   `cd dosbox`
   
   
   `cp fileNames.txt cscope.files`
   
   
   `mv cscope.files cscope`
   
   
   `cd cscope`
   
   
   `cscope -b -c -R` this produces cscope.out
   
   
   `cd tceetree`
   
   
   `./tceetree -i ../cscope.out` this produces tceetree.out which is a text call graph
   
   
   `dot -Tpng -O tceetree.out` this produces a png file to view the visual call graph
   
   
   `cd ../pagerank-master/cpp`
   
   
   `pagerank -d "->" ../../tceetree.out > pagerankScore.txt` this produces a list of page rank values for each function 
