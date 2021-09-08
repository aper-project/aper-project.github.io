---
layout: page
css: ["projects.css"]
# js: ["https://cdnjs.cloudflare.com/ajax/libs/geopattern/1.2.3/js/geopattern.min.js", "projects.js"]
---

---

|      Device Name     | Android Version |    App Name    | App Version |
|:--------------------:|:---------------:|:--------------:|:-----------:|
| Samsung Galaxy Note4 |      6.0.1      | OI Notepad |     1.5.4    |

---

{% include videopages/type1/syncopoli.html %}

##### Description

According to the official docs, the `getAccountsByType` API needs `GET_ACCOUNTS` permission.
However, the calling context does not involve either permission checking (via checkSelfPermission) nor permission request (via requestPermissions) to the corresponding permission, which causes the crash.

Reproduce crash:
1. enter the app's "Settings" menu item
2. edit the "Frequency (hours)" item, then leave the Settings by tapping "BACK"
3. repeat 1-2 (once or twice) and the app crashes

Crash trace:
```
04-29 16:28:35.240 6493-6493/? E/AndroidRuntime: FATAL EXCEPTION: main
    Process: org.amoradi.syncopoli, PID: 6493
    java.lang.NullPointerException: Attempt to invoke virtual method 'void org.amoradi.syncopoli.BackupActivity.setupSyncAccount()' on a null object reference
        at org.amoradi.syncopoli.SettingsFragment.onSharedPreferenceChanged(SettingsFragment.java:88)
        at android.app.SharedPreferencesImpl$EditorImpl.notifyListeners(SharedPreferencesImpl.java:479)
        at android.app.SharedPreferencesImpl$EditorImpl.apply(SharedPreferencesImpl.java:387)
        at android.preference.Preference.tryCommit(Preference.java:1649)
        at android.preference.Preference.persistString(Preference.java:1682)
        at android.preference.EditTextPreference.setText(EditTextPreference.java:106)
        at android.preference.EditTextPreference.onDialogClosed(EditTextPreference.java:172)
        at android.preference.DialogPreference.onDismiss(DialogPreference.java:424)
        at android.app.Dialog$ListenersHandler.handleMessage(Dialog.java:1533)
        at android.os.Handler.dispatchMessage(Handler.java:102)
        at android.os.Looper.loop(Looper.java:158)
        at android.app.ActivityThread.main(ActivityThread.java:7225)
        at java.lang.reflect.Method.invoke(Native Method)
        at com.android.internal.os.ZygoteInit$MethodAndArgsCaller.run(ZygoteInit.java:1230)
        at com.android.internal.os.ZygoteInit.main(ZygoteInit.java:1120)
```

##### Aper Outputs

```
API:
	<android.accounts.AccountManager: android.accounts.Account[] getAccountsByType(java.lang.String)>
---
PERMISSIONS:
	[android.permission.GET_ACCOUNTS]
---
CALLCHAIN:
	org.amoradi.syncopoli.BackupActivity.onCreate(android.os.Bundle)void
	 org.amoradi.syncopoli.BackupActivity.setup(boolean)void
	  org.amoradi.syncopoli.BackupActivity.setupSyncAccount()void
	   org.amoradi.syncopoli.BackupActivity.getOrCreateSyncAccount()android.accounts.Account
	    android.accounts.AccountManager.getAccountsByType(java.lang.String)android.accounts.Account[]

======

DANGEROUS: android.permission.GET_ACCOUNTS
	Is Declared: false
	Check Sites: NONE
	Request Sites: NONE
	Has Handle: in <org.amoradi.syncopoli.BackupActivity: void onRequestPermissionsResult(int,java.lang.String[],int[])>
```
