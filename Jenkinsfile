pipeline 
    {

        agent any

        stages
	     {

	         stage('Init')
		    
		    {
                       steps
		         
			  {

		           echo "Testing"
                          }

		    }

		  stage('Build')

		     {
                        steps
			   
			   {

		             echo "Building ..."
                           }

		     }

		  stage('Deploy')

		     {
                        steps

			   {

			      timeout(time:5,unit:'DAYS')
                                   {
				      input message:'Approve Production Deployment?'

				   }
                           
			       build job: 'Copying artifacts - apache'  
			   }

			   

		          post {
		                  success 
				  
				         {
					 
					    echo 'This will run only if successful'

					    mail (to: 'amarhmujumdar@gmail.com', 
					    subject: "Failed Pipeline: ${currentBuild.fullDisplayName}", 
					    body: "Something is wrong")
					 }
				 
				 failure 
				        
					 {
					
					    echo 'This will run only if failed'
					 }

			       }		 

		     }	


	     }

      }

