stage('Approve deployment on PRD') {
      when {
        branch 'master'
        environment name: 'DEPLOY_TST', value: "true"
        environment name: 'DEPLOY_UAT', value: "true"
      }
      steps {
        timeout(time: 14, unit: 'DAYS') {
          script {
           env.DEPLOY_PRD = input message: 'Approve deployment', parameters: [
              [$class: 'BooleanParameterDefinition', defaultValue: false, description: '', name: 'Approve deployment on PRD']
            ]
          }
        }
      }
    }
