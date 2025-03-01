Release Notes :

v1.0.1
    - Initial Release.
v1.0.2
    - Fixed Build issues.

    - SDK Versions :
        - Facebook SDK v9.2.0
        - Game Analytics SDK v6.5.7
        - Adjust SDK v4.29.1
        - Adjust Purchase SDK v1.0.3
        - ATT Enabled Using AppLovin Max SDK
        
v1.0.3
    - Fixed Build issues.
    - Game Analytics Ad Revenue Tracking Enabled.
    - Game Analytics IAP Reporting Integrated.
    
    - SDK Versions :
        - Facebook SDK v11.0.0
        - Game Analytics SDK v6.6.4
        - Adjust SDK v4.29.2
        - Adjust Purchase SDK v1.0.3
        - ATT Enabled Using AppLovin Max SDK

v1.0.4
    - Fixed Build issues.
    - Game Analytics Ad Revenue Tracking Enabled.
    - Game Analytics IAP Reporting Integrated.
    
    - SDK Versions :
        - Facebook SDK v11.0.0
        - Game Analytics SDK v7.3.17
        - Adjust SDK v4.29.5
        - Adjust Purchase SDK v1.0.3
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

NOTE :  This SDK Manager Module Also supports GDPR Consent SDK. Incase you're not using GDPR Consent SDK or not requires,
        You do not need to take any action.  The build-in editor code will handle these automatically.

        Once you add GDPR Consent SDK, SDKManager will Initialize after consent verification. SDKManager code has already
        provisions to handle this thing. you don't need to take any action again.


Basic Settings :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

How to configure :

1.  Import StartUp SDKs unity Package.

2.  Go To Tastypill ~> SDK Manager ~> SDK Settings.

3.  Enter Valid Keys to Game Analytics Settings and Press Apply Settings Button.

4.  Enter Valid Keys to Facebook Settings and Press Apply Settings Button.

5.  Enter Valid Adjust App Tokens for android and iOS.

6.  Go To "Assets ~> Adjust ~> Check iOS 14 Support Status". if disabled, please enable it by Selecting "Assets ~> Adjust ~> Toggle iOS 14 Support Status"

7.  Go To "Assets ~> Adjust ~> Check Post Processing Status". if disabled, please enable it by Selecting "Assets ~> Adjust ~> Toggle Post Processing Status"

8.  Open First scene of game.

9.  Go To Tastypill ~> SDK Manager ~> Create SDK Manager.

10.  Setup Complete.


Game Analytics Additional Settings :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
GameAnalytics need to pass Level Progression events manually. Please use SDKManager script component to report level progression events. Below is example.

    Level Start :
    --------------------------------------------------------
    SDKManager.Instance.OnLevelStartedEvent(int levelIndex);
    --------------------------------------------------------

    Level Complete :
    --------------------------------------------------------
    SDKManager.Instance.OnLevelCompletedEvent(int levelIndex);
    --------------------------------------------------------

    Level Fail :
    --------------------------------------------------------
    SDKManager.Instance.OnLevelFailEvent(int levelIndex);
    --------------------------------------------------------
    
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
IAP Purchase Reporting to Adjust and Game Analytics.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

1. Integrate IAP Purchase SDK and Configure purchases as per the requirements.

2. On Purchase Successful. Call below method to report and track IAP with adjust and Game Analytics.

3. To Validate and Report IAP to Adjust please call below method.

    ------------------------------------------------
    SDKManager.Instance.ValidateIAP(Product product);
    ------------------------------------------------

4.  To Validate and Report IAP to Game Analytics please call below method.
   
     ----------------------------------------------------------------------------
     SDKManager.Instance.ReportIAPToGameAnalyticsWithValidation(Product product);
     ----------------------------------------------------------------------------

Adjust Purchase SDK requires Unity IAP Sdk to be integrated within app. please follow below steps to configure and report
IAPs to adjust.

1.  Open SDK Manager Script and fill the "eventToken" values for all eventtoken. these event tokens can be grabbed from
    Adjust's dashboard.

2. Integrate IAP Purchase SDK and Configure purchases as per the requirements.

3. On Purchase Successful. Call below method to report and track IAP with adjust.

    -------------------------------------------------
    SDKManager.Instance.ValidateIAP(Product product);
    -------------------------------------------------
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Enable Apple App Tracking Using AppLovin Max
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
1. Install AppLovin Max SDK for unity.    
2. Goto "AppLovin" Menu Item On Unity Editor and Select "Integration Manager"
3. Navigate to "Privacy Settings".
4. Check "Enable Consent Flow (iOS Only") toggle.
5. Enter "https://tastypill.com/privacypolicy/" in Privacy Policy URL.
6. Keep Terms of Service URL Empty as its optional.
7. You can edit Description and localization content if you wish.
8. Open SDKManager.cs 
9. Look for "InitializeApplovin" method and Uncomment code inside it.
10. ATT prompt should be showing upon app launch now on iOS devices 14.5 or above.     
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
