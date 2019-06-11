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

			      timeoute(time:5,unit:"Days")
                                   {
				      inputmessage:'Approve Production Deployment'

				   }

			   }

			   Build job : 'Copying artifacts - apache'

		        steps
			
			{
			
			echo "Code Deployed..."
                        }

		     }	


	     }

      }

