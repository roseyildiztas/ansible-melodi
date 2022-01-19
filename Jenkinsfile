properties([
    parameters([
        string(defaultValue: '', description: 'Enter IP Address', name: 'hostip', trim: true)
        ])
    ])

node{
    stage("Pull Repo"){
        git 'https://github.com/roseyildiztas/ansible-melodi.git'
    }
    
    stage("Ansible"){
        ansiblePlaybook credentialsId: 'jenkins-master-ssh-key', disableHostKeyChecking: true, inventory: "${params.hostip},", playbook: 'main.yml'
    }
}
