

pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh('''
                    cat semver.sh
                    bash ./semver.sh validate 23.1.0-rc
                ''')
            }
        }
    }

    // post {
    //     always {
    //         script {
    //             // Generate a new version number using the semver library
    //             def version = new Semver("1.2.3")
    //                 .incrementPatch()
    //                 .setPreReleaseVersion("alpha")
    //                 .getValue()

    //             // Set the version number as an environment variable for use in later stages
    //             env.VERSION = version

    //             // Print the version number to the console
    //             echo "New version number: ${version}"
    //         }
    //     }
    // }
}