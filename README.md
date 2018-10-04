 stage ('post-flight checks') {

	// Run Blackduck scan
	// echo "====Running Blackduck Scan===="
	/**
	node ('DevServer') {	
	    withEnv(['SCAN_CLI_OPTS=-Dhttp.proxyHost=webgateway.info53.com -Dhttp.proxyPort=8080']) {
			echo "running Blackduck scan on build workspace ${WORKSPACE}"
			withCredentials([string(credentialsId: 'bd-cred', variable: 'bd-password')]) {
				bat '''set BD_HUB_PASSWORD=%bd-password%
					"D:\\Hub Scanner\\clients\\scan.cli-4.8.1\\bin\\scan.cli.bat" --username olad.oketade@53.com --host fifththird.blackducksoftware.com --port 443 --scheme HTTPS --project testCLIviaProxy --release 1 %WORKSPACE%
					'''
	 		}
		}
	} */
	// }
