pipeline {
    agent any
    stages {
      stage('test1 : Using when_01') {
        // when에서 설정한 조건이 True일 경우에만 steps이 실행된다.
        when { branch 'master' }  // branch가 master인 경우 다음 steps이 실행됨
        steps {
          echo 'It is executed'
        }
      }
      stage('test1 : Using when_02') {
        when { not { branch 'master' }} // branch가 master가 아닐 경우 다음 steps이 실행됨
        steps {
          echo 'It is not executed'
        }
      }
      stage('test3 : Using Script') {
        steps {
          // script 의 {} 태그 안에서 Groovy를 사용할 수 있게 해준다
          script {
            if (env.BRANCH_NAME == 'master') { // branch가 master일 경우 if문 안의 코드가 실행 
                for (i in 1 .. 5){ // 메시지를 5번 반복
                  echo 'I only execute on the master branch'
                }
            } else {  // branch가 master가 아닐 경우 if문 안의 코드가 실행 
                echo 'I execute elsewhere'
            }
          }
        }
      }
    }
}
