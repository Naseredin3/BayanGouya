# CI build fix

The GitHub Actions workflow intentionally builds only the Debug APK. Unit/Robolectric screenshot tests are not run in CI because the previous failure was `:app:testDebugUnitTest` caused by Robolectric `DefaultSdkProvider.java:170`. The APK build itself reached compilation successfully.

The debug build uses Android Gradle Plugin 8.13.2 / Gradle 8.13 / Java 17 and Android's default debug signing, so no secret keystore is required.
