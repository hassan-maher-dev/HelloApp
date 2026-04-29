pipeline {

    agent any
 
  
    stages {
 
        stage('Checkout Code') {

            steps {

                echo "🔹 Checking out repository..."

                git branch: 'main', url: 'https://github.com/mohamed55979/HelloApp'

            }

        }
 
        stage('Terraform Init') {

            steps {

                echo "🔹 Initializing Terraform..."

                sh 'terraform init -reconfigure'

            }

        }
 
        stage('Terraform Plan') {

            steps {

                echo "🔹 Creating Terraform plan..."

                sh 'terraform plan -out=tfplan'

            }

        }



        stage('Terraform Apply') {

            steps {

                echo "🔹 Applying Terraform..."

                sh 'terraform apply -auto-approve tfplan'

                echo "✅ Infrastructure deployed successfully!"

            }

        }



/*       stage('Terraform Destroy') {

            steps {

                echo "🗑️ Destroying Terraform infrastructure..."

                sh 'terraform destroy -auto-approve'

                echo "🔥 Infrastructure destroyed successfully!"

            }

        }

   }
*/ 
    post {

        success {

            echo "🎉 Pipeline completed successfully!"

        }

        failure {

            echo "❌ Pipeline failed!"

        }

    }

}
