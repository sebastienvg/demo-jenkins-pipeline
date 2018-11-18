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
    stage('stage2') {
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
            my_var: "$MYVAR" 
            my_user: "$MYUSER"'''
        )
        }
    }
}
