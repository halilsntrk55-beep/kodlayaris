# Firebase Auth and Realtime Database setup

The game now uses Firebase Authentication email/password accounts. Usernames are mapped to an internal Firebase email address; players do not need to enter a real email address. Password recovery must be handled by a project administrator.

Before relying on account login, make sure **Email/Password** is enabled under Firebase Authentication sign-in providers.

## Realtime Database rules

The game writes ownerUid beside each profile. Merge the following path into the existing Realtime Database rules object:

```json
{
  "kodlayaris_v1": {
    "profiles": {
      "$profileKey": {
        ".read": "auth != null && (!data.exists() || !data.child('ownerUid').exists() || data.child('ownerUid').val() == auth.uid)",
        ".write": "auth != null && newData.child('ownerUid').val() == auth.uid && (!data.exists() || !data.child('ownerUid').exists() || data.child('ownerUid').val() == auth.uid)"
      }
    }
  }
}
```

This is a snippet, not a replacement for the project's complete rules. The Firebase project is also used by UBİLSEM, so preserve its existing ubilsem_v1 rules. Remove any public read/write grant inherited from a parent path: parent grants override narrower child restrictions.

Profiles created before password accounts have no ownerUid. The first authenticated account that opens a legacy profile claims it by writing its UID. Once claimed, another account cannot change it under these rules. Until the broader rules are applied, an existing public grant may still expose legacy data.
