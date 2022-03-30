# compose-testing
[Compose Testing](https://developer.android.com/codelabs/jetpack-compose-testing)

## [1\. Introduction and setup](#0)

In this codelab you'll learn about testing UIs created with [Jetpack Compose](https://developer.android.com/jetpack/compose). You will write your first tests while learning about testing in isolation, debugging tests, semantics trees and synchronization.

## What you'll need

*   [Android Studio Bumblebee](https://developer.android.com/studio)
*   Knowledge of Kotlin
*   Basic understanding of Compose (such as the `@Composable` annotation)
*   Basic familiarity with [modifiers](https://developer.android.com/jetpack/compose/layouts/basics#modifiers)
*   Optional: Consider taking the [Jetpack Compose basics codelab](https://codelabs.developers.google.com/codelabs/jetpack-compose-basics/) before this codelab

### Check out the code for this codelab (Rally)

You're going to use the [Rally Material study](https://material.io/design/material-studies/rally.html#about-rally) as the base for this codelab. You'll find it in the android-compose-codelabs Github repository. To clone, run:

<devsite-code data-copy-event-label="" dark-code="" no-copy="">

    $ git clone https://github.com/googlecodelabs/android-compose-codelabs.git

</devsite-code>

Once downloaded, open the `TestingCodelab` project.

Alternatively, you can download two zip files:

*   [Starting point](https://github.com/googlecodelabs/android-compose-codelabs/archive/refs/heads/main.zip)
*   [Solution](https://github.com/googlecodelabs/android-compose-codelabs/archive/refs/heads/end.zip)

Open the TestingCodelab folder, which contains an app called Rally.

The compose-codelabs repo contains starter code for all codelabs in the pathway.

For this codelab, use the **TestingCodelab** project.

*   ![android_studio_folder.png](https://developer.android.com/codelabs/jetpack-compose-testing/img/6f0f6fd5cd023084.png) **TestingCodelab** — Project that contains the start and finished code for this codelab

The project is built in multiple git branches:

*   **main** – the starter code for this project, you will make changes to this to complete the codelab
*   **end** – contains the solution to this codelab

## Examine the project structure

Compose tests are instrumented tests. This means they require a device (physical device or emulator) to run on.

Rally already contains some Instrumented UI tests. You can find them in the androidTest source set:

![6f0f6fd5cd023084.png](/codelabs/jetpack-compose-testing/img/6f0f6fd5cd023084.png)

This is the directory where you'll place the new tests. Feel free to take a look at the `AnimatingCircleTests.kt` file to learn what a Compose test looks like.

Rally is already configured, but all you need to enable Compose tests in a new project is the testing dependencies in the `build.gradle` file of the relevant module, which are:

<devsite-code data-copy-event-label="" dark-code="" no-copy="">

    androidTestImplementation "androidx.compose.ui:ui-test-junit4:$version"debugImplementation "androidx.compose.ui:ui-test-manifest:$rootProject.composeVersion"

</devsite-code>

Note: For more information about how to set up testing in your Compose app, check out the [Testing documentation](https://developer.android.com/jetpack/compose/testing#setup).

Feel free to run the app and familiarize yourself with it.
