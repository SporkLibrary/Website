Spork is an annotation processing library to speed up development on your projects.<br/>
This allows you to write less boilerplate code to make code more readable and maintainable.

Spork is [fast](Benchmarks), [open-source](License_details) and it aims to be different by overcoming the shortcomings of its [alternatives](Comparison).

### Example

```java
@BindLayout(R.layout.activity_download)
public class DownloadActivity extends Activity {
	
	@BindView(R.id.download_button)
	private Button downloadButton;

	@BindFragment(R.id.details_fragment)
	private DetailsFragment fragment;

	@BindComponent
	private DownloadManager downloadManager;

	public void onCreate(Bundle savedInstanceState) {
		super.onCreate(savedInstanceState);
		Spork.bind(this); // Spork does its magic
	}

	@BindClick(R.id.other_button)
	private void onClickButton(Button button) {
		downloadManager.startDownload();
	}
}

@ComponentScope(scope = ComponentScope.Scope.SINGLETON)
public class DownloadManager {
	public void startDownload() { ... }
}
```

### Getting started

Add the following dependencies in `build.gradle`:

```groovy
dependencies {
    compile 'io.github.sporklibrary:spork:3.2.0'
    compile 'io.github.sporklibrary:spork-android:3.0.0@aar'

    // The following dependency is optional.
    // It requires you to also add: appcompat-v7, support-v4, recyclerview-v7
	compile 'io.github.sporklibrary:spork-android-support:3.0.0@aar' 
}
```

All dependencies are available at [Maven Central Repository](http://search.maven.org/#search%7Cga%7C1%7Cg%3A%22io.github.sporklibrary%22).

<!-- # Introduction

Spork is an annotation processing library to speed up development on your projects.<br/>
This allows you to write less boilerplate code to make code more readable and maintainable.

This library is [fast](about/benchmarks), [open-source](about/license) and it aims to be different by overcoming the shortcomings of its [alternatives](/about/comparison).

### Android Example

```java
@BindLayout(R.layout.activity_download)
public class DownloadActivity extends Activity {
	
	@BindView(R.id.download_button)
	private Button downloadButton;

	@BindFragment(R.id.details_fragment)
	private DetailsFragment fragment;

	@BindComponent
	private DownloadManager downloadManager;

	public void onCreate(Bundle savedInstanceState) {
		super.onCreate(savedInstanceState);
		Spork.bind(this); // Spork does its magic
	}

	@BindClick(R.id.other_button)
	private void onClickButton(Button button) {
		downloadManager.startDownload();
	}
}
```

### Getting started with Android

Add the following dependencies in `build.gradle`:

```groovy
repositories {
	jcenter()
}

dependencies {
    compile 'io.github.sporklibrary:spork-inject:4.0.0'
    compile 'io.github.sporklibrary:spork-android:4.0.0@aar'
    // Optional, requires you to also add: appcompat-v7, support-v4, recyclerview-v7:
	compile 'io.github.sporklibrary:spork-android-support:4.0.0@aar' 
}
```

### Getting started with Java

Add the following dependencies in `build.gradle`:

```groovy
dependencies {
    compile 'io.github.sporklibrary:spork-inject:4.0.0'
}
```

All dependencies are available at [JCenter](https://bintray.com/bintray/jcenter).
 -->