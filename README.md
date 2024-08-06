# Eclipse-Network-issues
Eclipse-Network-issues

### Eclipse Marketplace not opening

**If you ever facing network issue with eclipse then we can resolve the issue as below steps.**
If you ever facing this below error
**Cannot open Eclipse Marketplace:**
```
Cannot install remote marketplace locations: Cannot complete request to https://marketplace.eclipse.org/catalogs/api/p: PKIX path building failed: sun.security.provider.certpath.SunCertPathBuilderException: unable to find valid certification path to requested target
Cannot complete request to https://marketplace.eclipse.org/catalogs/api/p: PKIX path building failed: sun.security.provider.certpath.SunCertPathBuilderException: unable to find valid certification path to requested target
PKIX path building failed: sun.security.provider.certpath.SunCertPathBuilderException: unable to find valid certification path to requested target
PKIX path building failed: sun.security.provider.certpath.SunCertPathBuilderException: unable to find valid certification path to requested target
PKIX path building failed: sun.security.provider.certpath.SunCertPathBuilderException: unable to find valid certification path to requested target
PKIX path building failed: sun.security.provider.certpath.SunCertPathBuilderException: unable to find valid certification path to requested target
Cannot complete request to https://marketplace.eclipse.org/catalogs/api/p: PKIX path building failed: sun.security.provider.certpath.SunCertPathBuilderException: unable to find valid certification path to requested target
PKIX path building failed: sun.security.provider.certpath.SunCertPathBuilderException: unable to find valid certification path to requested target
PKIX path building failed: sun.security.provider.certpath.SunCertPathBuilderException: unable to find valid certification path to requested target
PKIX path building failed: sun.security.provider.certpath.SunCertPathBuilderException: unable to find valid certification path to requested target
PKIX path building failed: sun.security.provider.certpath.SunCertPathBuilderException: unable to find valid certification path to requested target
```
**In this case we can't access internet as well can't open market place and eclipse.** 
### Here is one test class I am going to copy paste here.

```
package com;

import java.net.URL;
import java.net.URLConnection;

public class InternetChecker {
    public static boolean isConnected() {
        try {
            URL url = new URL("http://www.google.com"); // Replace with any reliable website
            URLConnection connection = url.openConnection();
            connection.connect();
            return true;
        } catch (Exception e) {
        	System.out.println(e);
            return false;
        }
    }

    public static void main(String[] args) {
        if (isConnected()) {
            System.out.println("Internet is connected");
        } else {
            System.out.println("Internet is not connected");
        }
    }
}

```



### If in this case facing network issue or as per above warning errors. We can setup in eclipse flags.
in this file in root directory of eclipse.exe 
### `eclipse.ini`
Let's see here:

> First below line is enable to access internet for java program. Outcome will be internet is connected message will show! If you have already showing it then not need to use below first line.

```
-Djava.net.preferIPv4Stack=true
```

> In the below two line is Storing for SSL certification verification. Outcome will be access marketplace!

```
-Djavax.net.ssl.trustStoreType=Windows-ROOT 
-Djavax.net.ssl.trustStore=NONE
```

**Full Changelog**: https://github.com/ugale-deepak3010/Eclipse-Network-issues/commits/v1.0_Eclipse_MarketPlace_Error
