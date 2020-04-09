node {
  stage('Git clone') {
    git(url: 'https://github.com/pe-woongjin/ami.git', branch: "${branch}", changelog: true)
  }
  dir ("packer/build_${OS_Type}") { 
    stage ('packer') {
      sh '''
      /opt/packer/packer build ./${Target_Image}-ami.json
      '''
    }
  }
}
parameters {
  string(name: 'branch', defaultValue: 'develop', description: '디플로이할 대상 브랜치를 입력하세요.')  
}
