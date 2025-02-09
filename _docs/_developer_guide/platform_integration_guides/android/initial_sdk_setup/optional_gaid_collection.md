---
nav_title: Google Advertising ID (Optional)
article_title: Optional Google Advertising ID for Android
page_order: 9
platform: 
  - Android
description: "This reference article covers Google advertising IDs and how to pass this advertising information to Braze for your Android or FireOS application."

---

# Google Advertising ID (Android only)

> The [Google Advertising ID](https://support.google.com/googleplay/android-developer/answer/6048248/advertising-id?hl=en) is an optional user-specific, anonymous, unique, and resettable ID for advertising, provided by Google Play services. This reference article covers Google advertising IDs and how to pass this advertising information to Braze for your Android or FireOS application.

GAID gives users the power to reset their identifier, opt-out of interest-based ads within Google Play apps, and provides developers with a simple, standard system to continue to monetize their apps.

## Passing the Google Advertising ID to Braze

The Google Advertising ID is not automatically collected by the Braze SDK and must be set manually via the [`Braze.setGoogleAdvertisingId()`](https://braze-inc.github.io/braze-android-sdk/kdoc/braze-android-sdk/com.braze/-i-braze/set-google-advertising-id.html) method.

{% alert important %}
Google requires the Advertising ID to be collected on a non-UI thread.
{% endalert %}

{% tabs %}
{% tab JAVA %}

```java
new Thread(new Runnable() {
  @Override
  public void run() {
    try {
      AdvertisingIdClient.Info idInfo = AdvertisingIdClient.getAdvertisingIdInfo(getApplicationContext());
      Braze.getInstance(getApplicationContext()).setGoogleAdvertisingId(idInfo.getId(), idInfo.isLimitAdTrackingEnabled());
    } catch (Exception e) {
      e.printStackTrace();
    }
  }
}).start();
```

{% endtab %}
{% tab KOTLIN %}

```kotlin
Thread(Runnable {
  try {
    val idInfo = AdvertisingIdClient.getAdvertisingIdInfo(getApplicationContext())
    Braze.getInstance(getApplicationContext()).setGoogleAdvertisingId(idInfo.id, idInfo.isLimitAdTrackingEnabled)
  } catch (e: Exception) {
    e.printStackTrace()
  }
}).start()
```

{% endtab %}
{% endtabs %}


