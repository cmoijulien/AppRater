![JitPack](https://jitpack.io/v/cmoijulien/AppRater.svg)

# AppRater

AppRater is a library for Android designed to facilitate easy prompting of users to rate your app within the Google Play store or Amazon App Store.
It won't prompt until at least 3 days or 7 uses of the app has passed and if the user chooses to rate later the count will start again.

To use simply add the library to your app and make one call within your onCreate method as follows;

`AppRater.app_launched(this);`

There are several options you can also use to change the default behavior.

You can use the overriden method to specify your own day and launch count parameters.
`setVersionCodeCheckEnabled` or `setVersionNameCheckEnabled` enable version checking, which will re-enable the prompt count if a new version is installed.
`isNoButtonVisible` will disable the No Thanks button, forcing the user to either rate or prompt later.

By default this will link to the Google Play store.  You can optionally set an alternate market by using;

`AppRater.setMarket(new GoogleMarket());`

`AppRater.setMarket(new AmazonMarket());`

You can implement your own market, implementing the Market interface and parse your URI.

If you want to have a "Rate Now" menu option to go straight to your play store listing call `AppRater.rateNow(this);` within your menu code.

Try out the demo within this repository.

## Gradle

Step 1. Add the JitPack repository to your build file

Add it in your root build.gradle at the end of repositories:

	allprojects {
		repositories {
			...
			maven { url 'https://jitpack.io' }
		}
	}

Step 2. Add the dependency

	dependencies {
		implementation 'com.github.cmoijulien:AppRater:1.0.2'
	}

## Translations

If you would like to help localise this library please fork the project, create and verify your language files, then create a pull request to the translations branch.

## Contributing Code

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request
