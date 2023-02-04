pipeline {
    agent none
    stages {
        stage('Backups - VM image permissions') {
            agent {
                label "HQDEBDEV01"
            }
            steps {
                sh"""
                sudo su cblock -c "source ~/.profile; vm_shutdown || exit 0"
                """
            }
        }
                stage('Backups - DEV HDD 10TB (KVM images)') {
            agent {
                label "HQDEBDEV01"
            }
            steps {
                sh"""
                sudo su cblock -c "source ~/.profile; rsync_nas_two || exit 0"
                """
            }
        }
    }
}
