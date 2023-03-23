// pipeline {
//     agent any
//     environment {
//         VERSION_FILE = 'version.txt'
//         MAJOR_VERSION = 0
//         MINOR_VERSION = 0
//         PATCH_VERSION = 0
//         VERSION_TAG = ""
//     }
//     stages {
//         stage('Checkout') {
//             steps {
//                 checkout scm
//             }
//         }
//         stage('Parse version') {
//             steps {
//                 script {
//                     def versionContent = readFile(VERSION_FILE)
//                     def versionParts = versionContent.trim().split('\\.')
//                     MAJOR_VERSION = versionParts[0].toInteger()
//                     MINOR_VERSION = versionParts[1].toInteger()
//                     PATCH_VERSION = versionParts[2].toInteger()
//                 }
//             }
//         }
//         stage('Bump version') {
//             steps {
//                 script {
//                     def buildNumber = env.BUILD_NUMBER.toInteger()
//                     if (env.BRANCH_NAME == 'master') {
//                         MAJOR_VERSION += 1
//                         MINOR_VERSION = 0
//                         PATCH_VERSION = 0
//                         VERSION_TAG = "v${MAJOR_VERSION}.${MINOR_VERSION}.${PATCH_VERSION}"
//                     } else if (env.BRANCH_NAME == 'develop') {
//                         MINOR_VERSION += 1
//                         PATCH_VERSION = 0
//                         VERSION_TAG = "v${MAJOR_VERSION}.${MINOR_VERSION}.${PATCH_VERSION}-SNAPSHOT"
//                     } else {
//                         PATCH_VERSION += 1
//                         VERSION_TAG = "v${MAJOR_VERSION}.${MINOR_VERSION}.${PATCH_VERSION}-SNAPSHOT"
//                     }
//                 }
//             }
//         }
//         stage('Update version file') {
//             steps {
//                 script {
//                     writeFile file: VERSION_FILE, text: "${MAJOR_VERSION}.${MINOR_VERSION}.${PATCH_VERSION}"
//                 }
//             }
//         }
//         stage('Commit and tag') {
//             steps {
//                 sh "git commit -am 'Bump version to ${MAJOR_VERSION}.${MINOR_VERSION}.${PATCH_VERSION}'"
//                 sh "git tag ${VERSION_TAG}"
//             }
//         }
//     }
// }


// pipeline {
//     agent any
//     environment {
//         VERSION_FILE = 'version.txt'
//         MAJOR_VERSION = 0
//         MINOR_VERSION = 0
//         PATCH_VERSION = 0
//         VERSION_TAG = ""
//     }
//     stages {
//         stage("Check version"){
//             steps {
//                 script {

//                 }
//             }
//         }
//     }
// }

pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        script {
          def currentVersion = semver( incrementVersion: 'PATCH', 
                                       version: '1.2.3')
          echo "Current version is: ${currentVersion}"
        }
      }
    }
  }
}