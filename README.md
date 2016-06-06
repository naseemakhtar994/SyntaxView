# SyntaxView
Code beautifier for Android - a wrapper around a WebView running [HighlightJS](https://highlightjs.org/)

#Usage

Add the READ_EXTERNAL_STORAGE permission to your manifest.xml and add the [runtime permission to your Activity/Fragment](https://developer.android.com/training/permissions/requesting.html):

```xml
<uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE"/>
```

Add to your Android layout xml:
```xml
<eu.fiskur.syntaxview.SyntaxView
    android:id="@+id/syntaxview"
    android:layout_width="match_parent"
    android:layout_height="match_parent"/>
```

Initialise as usual:
```java
SyntaxView syntaxView = (SyntaxView) findViewById(R.id.syntaxview);
```

Display code string:
```java
String helloWorld = "private static final String helloWorld = \"HelloWorld!\";";
syntaxView.loadString(helloWorld, "java");
```

Load file:
```java
syntaxView.loadFile(file);
```

#Themes

All [HighlightJS](https://highlightjs.org/) themes are available:
```java
String[] themes = syntaxView.themes();
...
syntaxView.setTheme("monokai");
```

You can also set the theme when you pass the code arguments:
```java
String helloWorld = "private static final String helloWorld = \"HelloWorld!\";";
syntaxView.loadString("monokai", helloWorld, "java");

//for a file:
syntaxView.loadFile("monokai", file);
```

