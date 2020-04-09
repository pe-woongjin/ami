node {
  stage('Git clone') {
    git(url: 'https://github.com/pe-woongjin/ami.git', branch: "${branch}", changelog: true)
  }
  dir ("packer") { 
    stage ('packer') {
      sh '''
      /opt/packer/packer build ./default.json
      '''
    }
  }
}
parameters {
  string(name: 'branch', defaultValue: 'develop', description: '디플로이할 대상 브랜치를 입력하세요.')  
}
