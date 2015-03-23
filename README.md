# Scala FTP

A small library for working with FTP in Scala

```scala

object E {

	private val client: FTP = FTPClient() // create a new FTP client instance

	def downloadFileExample() : Unit = {

		client.connectWithAuth("ftp.mozilla.org", "anonymous", "")

		client.cd("pub")

		//Download file
		if (client.filesInCurrentDirectory.contains("README")) {
			client.downloadFile("README")
		}

		//Upload file
		if (client.filesInCurrentDirectory.contains("README")) {
			val fileStream: InputStream = ftp.downloadFileStream("README")
			client.uploadFile("README_REUPLOADED", fileStream)
		}

		client.disconnect()

	}

}

```