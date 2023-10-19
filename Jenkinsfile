pipeline {
    agent {
        label 'ansible'
    }
    stages {
        stage('Install requirements') {
            steps {
                sh 'pip3 install "molecule==3.5.2"'
                sh 'pip3 install "molecule_docker==1.1.0" "molecule_podman==1.1.0"'
                sh 'pip3 install ansible-lint yamllint'
                sh 'pip3 install ansible-lint yamllint'
                sh 'ansible-galaxy collection install community.docker:2.7.6'
                sh 'pip3 install "requests==2.24.0"'
            }
        }

        stage('Molecule test') {
            steps {
                sh 'cd playbooks/roles/vector-role && molecule test'
            }
        }
    }
}
