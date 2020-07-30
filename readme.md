# Renewal
**Renewal** is a library for updating your Java app.

_it's the concept_

## Getting started
Define **renewal** in dependencies:
`build.gradle`
```groovy
implementation 'com.nikialeksey:renewal:0.0.1'
```
Start renewal in your `psvm` with your app:
`App.java`
```java
public class App {
    public static void main(final String[] args) {
        new YourApp().start();
 
        final String currentVersion = "0.0.1";
        new Renewal(
            new Maven("com.yourdomain:yourbinary"), 
            currentVersion
        ).watch();
    }
}
```
When you publish a new version (`0.0.2` for example) of your app in the
maven (in this case), then **renewal** downloads it and restarts the java app 
process with the next version of your app.