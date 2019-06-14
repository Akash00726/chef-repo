pipeline {
  agent any
  stages {
    stage('test with cookstyle') {
      steps {
        chef_cookbook_cookstyle(installation: '/usr/bin/cookstyle')
      }
    }
    stage('test with foodcritic') {
      steps {
        chef_cookbook_foodcritic(installation: '/usr/local/bin/foodcritic')
      }
    }
    stage('error') {
      steps {
        dir(path: '/home/akash/Downloads/chef-rep/') {
          sh 'knife ssh clientnode --ssh-user root --ssh-password toor "chef-client"'
        }

      }
    }
  }
}