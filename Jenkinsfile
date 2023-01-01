pipeline {
    agent any

    stages {
        stage('deploy php file') {
            steps {
                sshPublisher(publishers: [sshPublisherDesc(configName: 'jenkinsserver', transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: '', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '/var/www/html/', remoteDirectorySDF: false, removePrefix: 'website/', sourceFiles: '**/*.php')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])
            }
        }
        stage('creating image  php file') {
            steps {
                sshPublisher(publishers: [sshPublisherDesc(configName: 'jenkinsserver', transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: 'sudo ansible-playbook dockerimagebuild.yaml', execTimeout: 220000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '/root', remoteDirectorySDF: false, removePrefix: '', sourceFiles: 'Dockerfile,deployapplication2.yaml,dockerimagebuild.yaml')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])
            }
        }
    }
}
