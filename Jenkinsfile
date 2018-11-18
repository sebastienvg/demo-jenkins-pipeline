node {
    /*
     stage('Update Inventory') {
        wrap([$class: 'AnsiColorBuildWrapper', colorMapName: "xterm"]) {
        ansibleTower(
            towerServer: 'awx_web',
            jobTemplate: '8',
            importTowerLogs: true,
            inventory: '',
            jobTags: '',
            limit: '',
            removeColor: false,
            verbose: true,
            credential: '',
            extraVars: '''---
            my_var: "$MYVAR"'''
        )   
        }
    }
    */
    
    stage('pull vaulted file') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], 
                         userRemoteConfigs: [[url: 'http://git-server/user/repository.git']] credentialsId: 'a4f220a9-4744-4b2a-bddb-bf080e3a2871']]]
            }
    
    stage('Running Demo Template on AWX local container') {
        wrap([$class: 'AnsiColorBuildWrapper', colorMapName: "xterm"]) {
        ansibleTower(
            // AWX instance defined in Jenkins
            towerServer: 'awx_web',
            // AWX Job ID or Name
            jobTemplate: '8',
            // true if you need to bring to Jenkins the logs from AWX
            importTowerLogs: true,
            // Inventory ID or Name, if undifined it will use the default template inventory (if any)
            inventory: '',
            // the Ansible TAGS you want to pass to AWX
            jobTags: '',
            // If you'd like to limit the targets to specific host(s)
            limit: '',
            // to remove colors in the terminal output
            removeColor: false,
            // true or false
            verbose: true,
            // if undifined will use the job's default (if any).
            credential: '',
            // Ansible --etra-vars (below MYVAR & MYUSER and defined by Jenkins prompt when you run.
            extraVars: '''---
            my_var: "$MYVAR" 
            my_user: "$MYUSER"'''
        )
        }
    }
}
