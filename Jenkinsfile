pipeline  {
agent any
stages {
	stage("Git-Checkout") {
		steps {
			echo "Checking out from Git repo";
			git 'https://github.com/Lararoft19/Pipeline_Script.git'
		}
	}

stage ("Build") {
	steps {
		echo "Building the checked-out project!";
		bat 'Build.bat'
	}
}

stage ("Unit Test") {
	steps {
		echo "Running JUnit Tests";
		bat 'Unit.bat'
		}
	}

stage ("Quality Gate") {
	steps {
		echo "verifying Quality Gates";
		bat 'Quality.bat'
		}
	}
	
stage ("Deploy") {
	steps {
		echo "Deploying to stage Environment for more tests!";
		bat 'Deploy.bat'
		}
		
	}
}

post {
	always {
		echo "This will always run"
	}
	success {
	echo "This will run only if successful"
	}
	failure {
	echo "This will run only if failed"
	}
	unstable {
	echo "This will run only if the run was marked as unstable"
	}
	changed {
	echo "This will run only if the state of the Pipeline has changed"
	echo "For example, if the Pipeline was previously failing but is now successful"
	}
}
}

