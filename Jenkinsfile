pipeline{
agent any

tools{
maven 'mymaven'
}

stages{
    

stage('test Code')
{
steps{
        script{   // groovy script
                  // declare 3 variables which will store number value
        int  maxRetries = 3   // int = integer = data type store in variable maxRetries 
        int retries = 0  
        boolean success = false

// we are using a keyword called as while which is representing a loop

      while(retries<maxRetries && !success){

          try{
                 sh 'mvn tst'  // risk code that will fail
                 success = true // if execution of above line is successful then exit the loop
          }
          catch(Exception e){
                retries++  // increment the value of retries by 1
                echo "Attempt ${retries} failed. Retrying.."  
                sleep(10)  // wait for 10 seconds before retrying
          }
      
      }  
      if(!success)  // execution of the steps have failed 
      {
      error("All attempts have failed")
      }
      
        
        }
}
}


}
}
