// This shows a simple example of how to archive the build output artifacts.
node('mac') {
    
    env.NODEJS_HOME = "${tool 'node9.11.2'}"
    // on linux / mac
    env.PATH="${env.NODEJS_HOME}/bin:${env.PATH}"
    
    stage "Create build output"
    
    // Make the output directory.
    sh "mkdir -p output"

    // Write an useful file, which is needed to be archived.
    writeFile file: "output/usefulfile.txt", text: "This file is useful, need to archive it."

    // Write an useless file, which is not needed to be archived.
    writeFile file: "output/uselessfile.md", text: "This file is useless, no need to archive it."

    stage "Test Newman"
    
    //this step runs newman
    sh '''
    npm install newman -g
    newman run http://bit.ly/2VQV2LS
    '''
    
    stage "Archive build output"
    
    // Archive the build output artifacts.
    archiveArtifacts artifacts: 'output/*.txt', excludes: 'output/*.md'
}
