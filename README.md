ContactsEditor Legacy
=====================

This contacts editor is the same as the one in official Contacts app in Android 2.3.3.

The editor is modified to support external accounts (Other account than Google and Exchange)


## Usage

This editor is an Android library. To use it :

 - Add the project library to the list of dependencies of your main application
 - Add theses lines in your Manifest file (manifest tag) :

```xml

    <uses-permission android:name="android.permission.READ_CONTACTS" />
    <uses-permission android:name="android.permission.WRITE_CONTACTS" />
    <uses-permission android:name="android.permission.GET_ACCOUNTS" />
```

 - Add theses lines in your Manifest file (application tag) :

```xml
        <activity
            android:name="com.android.contacts.ui.EditContactActivity"
            android:windowSoftInputMode="stateHidden|adjustResize">

            <intent-filter android:label="Edit with ContactEditorLegacy">
                <action android:name="android.intent.action.EDIT" />
                <category android:name="android.intent.category.DEFAULT" />
                <data android:mimeType="vnd.android.cursor.item/person" android:host="contacts" />
                <data android:mimeType="vnd.android.cursor.item/contact" android:host="com.android.contacts" />
                <data android:mimeType="vnd.android.cursor.item/raw_contact" android:host="com.android.contacts" />
            </intent-filter>

            <intent-filter android:label="Insert with ContactEditorLegacy">
                <action android:name="android.intent.action.INSERT" />
                <category android:name="android.intent.category.DEFAULT" />
                <data android:mimeType="vnd.android.cursor.dir/person" />
                <data android:mimeType="vnd.android.cursor.dir/contact" />
                <data android:mimeType="vnd.android.cursor.dir/raw_contact" />
            </intent-filter>

        </activity>
```

