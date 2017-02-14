#TODO
DOSBox


1.	To retrieve the requirements from the HTML:


  `cd dosbox`
  `./grabHtml.py > requirements.txt`
  `./convertReqstoList.py > finalRequirements.txt`


2.	To extract function information:


  `cd stereocode-master`
  `./stereocode –i dosboxUnformatted.xml –f ../../dosbox/dosboxInfo.csv`


3. To create the call graph:

   `cd dosbox`
   
   
   `cp fileNames.txt cscope.files`
   
   
   `mv cscope.files cscope`
   
   
   `cd cscope`
   
   
   `cscope -b -c -R`
   
   
   `cd tceetree`
   
   
   `./tceetree -i ../cscope.out`
   
   
   `dot -Tpng -O tceetree.out`
   
   
   `cd ../pagerank-master/cpp`
   
   
   `pagerank -d "->" ../../tceetree.out`
