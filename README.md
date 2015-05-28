#Lock Screen

Lock Screen is a website to demonstrate Windows 10 Web Hosted Apps. To use it you need to

- Publish this website to any server on the web
- Create a Windows 10 Universal App (JavaScript)
- Modify the package.appxmanifest to point to the URL the Web App is hosted
- modify the package.appxmanifest to allow URL access and Windows Runtime Access to the web content

## Sample entries

The following entries have to be in your package.appxmanifest

	<Application Id="App" StartPage="http://xyz.com">

Where `http://xyz.com` points to your hosted web app

additionally you have to add the content rules

	<uap:ApplicationContentUriRules>
		<uap:Rule Match="http://xyz.com" Type="include" WindowsRuntimeAccess="all"/>
	</uap:ApplicationContentUriRules>

Now the app is able to open the local file picker and change your lock screen background
