# Privacy Policy/License Android Activity.
Adds a license\privacy policy activity to your app.
This library is easily configurable and very convenient if you have multiple apps on Google Play, which need a Privacy Policy added.

## How to use

* Download the repo, assemble the library, than follow next steps below.

* Add to the main build.gradle file:

```
buildscript { 
    repositories { 
        mavenCentral() 
    } 

    dependencies {
        ... 
        classpath 'com.jakewharton:butterknife-gradle-plugin:8.5.1'
        ... 
    }
 }
```

* Add to the settings.gradle:

```
include ':app', ':license-release' 
```

* Add to the app's build.gradle file:

```
dependencies {
    ... 
    compile project(':license-release')
    ... 
}
```

* Create for simplicity a new xml values file and add a string resource (you can use html):

```
<string name="license">     
    <![CDATA[         
        <body>
		    <h2>Privacy Policy</h2>         		
		    ...         
        </body>     
    ]]>
 </string>
```

* The best place to add a link to this new activity is in the options menu:

```
public boolean onOptionsItemSelected(MenuItem item) {
    int id = item.getItemId();
    switch (id) {
        ...
        case R.id.action_license:
            startActivity(new Intent(this, LicenseActivity.class));
            return true;
        ...
    }
    return super.onOptionsItemSelected(item);
}
```

## Additional information


License
-------

	The MIT License (MIT)

	Copyright (c) 2017 Dmytro Karataiev

	Permission is hereby granted, free of charge, to any person obtaining a copy
	of this software and associated documentation files (the "Software"), to deal
	in the Software without restriction, including without limitation the rights
	to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
	copies of the Software, and to permit persons to whom the Software is
	furnished to do so, subject to the following conditions:

	The above copyright notice and this permission notice shall be included in all
	copies or substantial portions of the Software.

	THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
	IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
	FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
	AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
	LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
	OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
	SOFTWARE.
