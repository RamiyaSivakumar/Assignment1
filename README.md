# Assignment1
Assignment1- WordCloud
The steps that were followed to create the wordcloud were as follows: 
  
  Step 1: The code that allows for searching and retrieval of information from the ncbi database was copied to the terminal. 
  
  cd ~
  /bin/bash
  perl -MNet::FTP -e \
    '$ftp = new Net::FTP("ftp.ncbi.nlm.nih.gov", Passive => 1);
     $ftp->login; $ftp->binary;
     $ftp->get("/entrez/entrezdirect/edirect.tar.gz");'
  gunzip -c edirect.tar.gz | tar xf -
  rm edirect.tar.gz
  builtin exit
  export PATH=${PATH}:$HOME/edirect >& /dev/null || setenv PATH "${PATH}:$HOME/edirect"
  ./edirect/setup.sh
  
  When the installation was complete an output specifying that was presented. 
  
  Step 2: The sucessful installation of the code was tested using the test search of "lycopene cyclase" 
  
  esearch -db pubmed -query "lycopene cyclase" |   efetch -format abstract
  
  The output of this step resulted in multiple abstracts related to search being presented
  
  Step 3: The search was modified to the topic of choice of "Skin Microbiome" using the code line
  
  esearch -db pubmed -query "skin microbiome" |   efetch -format abstract
  
  Step 4: The results of the search query were directed to a text file using the following line of code
  
  esearch -db pubmed -query "skin microbiome" |   efetch -format abstract > pubmed.new.v1.txt
  
  Step 5: In vi, the "line enters" were removed. Line enters are written in code as "\n". 
   In order to do so, the code for replacing was used. 
   %s/\n\\g
   g specifies that this is to be done to all line enters present in the entire text file
   
   Step 6: The program for creating a wordcloud was pip installed 
   pip installation requires the following command " pip intall wordcloud" 
   
   Step 7: The confirmation that an image file containing the wordcloud was created was done using the "ls" command. 
   The presence of a file of that name was observed. 
   
   Step 8: The file was accessed from the local server and saved 
   
   
  
