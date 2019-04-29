
node('node') {
    try {
       stage('Checkout'){
          checkout scm
       }

       stage('Test'){
         sh 'bin/etrata ./requirements.txt'
         sh 'pip install -r requirements.txt'
         sh 'bin/afl .'
         sh 'bin/bandit .'
         sh 'bin/skaas .'
       }
    }
    catch (err) {
        throw err
    }

}
