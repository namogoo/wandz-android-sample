Wandz Android Demo
==================

<img src="https://app.wandz.ai/assets/wandzLogoText-GmXTmWRx.svg" alt="Wandz.ai">

The Wandz.ai SDK library for Android empowers developers to integrate advanced predictive AI capabilities into mobile applications effortlessly. By leveraging real-time data and machine learning models, the SDK enables personalized, in-session predictions tailored to each user's behavior. This ensures that your app delivers the right content, offers, and experiences at the optimal moment, enhancing user engagement and conversion rates.
Designed for flexibility and ease of use, the Wandz.ai SDK allows developers to seamlessly incorporate predictive analytics without extensive coding or technical overhead. The SDK integrates smoothly with existing Android applications, offering robust features to track and analyze user interactions in real-time. With built-in support for GDPR and CCPA compliance, Wandz.ai ensures that user privacy is maintained while delivering high-impact, data-driven insights to optimize every step of the customer journey.

Download
--------
For detailed instructions and requirements, see Wandz's [download and setup docs page][1].

You can download a jar using Gradle:

```gradle
repositories {
  google()
  mavenCentral()
}

dependencies {
  implementation 'ai.wandz.android:core-wandz:1.0.30'
}
```

Or Maven:

```xml
<dependency>
  <groupId>ai.wandz.android</groupId>
  <artifactId>core-wandz</artifactId>
  <version>1.0.30</version>
</dependency>
```

How to use Wandz?
-------------------
Before starting to use the Wandz SDK, you need to get an account ID in order to activate Wandz on your application and for accessing the [Wandz.ai][2] portal. You will need to add your account ID to your AndroidManifest.xml file using a meta-data tag.
Contact us at [Wandz.ai][3] to get your account ID.
Check out the [documentation][4] for pages on a variety of topics.

AndroidManifest example:
```xml
<application>
    ...
    <meta-data android:name="ai.wandz.sdk.client_id" android:value="YOUR_CLIENT_ID" />
</application>
```

Simple use cases will look something like this:

```kotlin
class App : android.app.Application() {
    override fun onCreate() {
        super.onCreate()

        //make sue to add the following line to your AndroidManifest.xml
        // <meta-data android:name="ai.wandz.sdk.client_id" android:value="%KEY_VALUE%" />
        WandzClient.start(applicationContext)
    }
}

class ProductActivity : AppCompatActivity() {
    private lateinit var binding: ActivityMainBinding

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)

        //report screen entered event to Wandz SDK
        //this event is used to track user navigation in the app
        WandzClient.reportScreenEnteredEvent(AppSection.CATEGORY, "Jeans", this)
    }
}
```

Compatibility
-------------

* **Minimum Android SDK**: Wandz requires a minimum API level of 21.

* **Activate**: There is an optional dependency available called `activate-wandz` that is used to display in-app messages/Coupons/Forms and more
* **Autocapture**: There is an optional dependency available called `autocapture-wandz`, that is used to automatically capture user journey in the app

Development
-----------
To open the project in Android Studio:

1. Go to *File* menu or the *Welcome Screen*
2. Click on *Open...*
3. Navigate to the Wandz root directory.
4. Select the `build.gradle` file in the root directory.
5. Sync the project with Gradle files.

Getting Help
------------
To report a specific problem or feature request, [open a new issue via our contact form][5]. For questions, suggestions, or
anything else, email [Wandz support][6].

Author
------
Ehud Lavin - @ehudlavin on GitHub

License
-------
BSD, part MIT and Apache 2.0. See the [LICENSE][7] file for details.

[1]: https://wandz.ai
[2]: https://app.wandz.ai/login
[3]: https://wandz.ai/contact-us
[4]: https://wandz.ai/use-cases
[5]: https://wandz.ai/contact-us
[6]: mailto:support@wandz.ai
[7]: https://github.com/namogoo/wandz-android-sample/blob/main/LICENSE