# Security and Privacy Questionnaire for Captured Surface Control

## Questions to Consider

### 2.1. What information might this feature expose to Web sites or other parties, and for what purposes is that exposure necessary?

Given a Web application `WA` that has used pre-existing means (`getDisplayMedia()`) to capture a tab `T`, and that therefore has access to all of `T`'s pixels, this feature exposes to `WA`:
1. `T`'s zoom-level. (This is exposed without another permission policy or prompt).
2. Potentially, additional pixels in `T`, if the user grants permission to forward gestures from `WA` to `T`, and/or allow `WA` to change `T`'s zoom-level.

### 2.2. Do features in your specification expose the minimum amount of information necessary to enable their intended uses?

Yes.

### 2.3. How do the features in your specification deal with personal information, personally-identifiable information (PII), or information derived from them?

Not applicable.

### 2.4. How do the features in your specification deal with sensitive information?

Not applicable.

### 2.5. Do the features in your specification introduce new state for an origin that persists across browsing sessions?

Yes - the state of the permission policy introduced by this spec, `"captured-surface-control"`.  
Otherwise - no.

### 2.6. Do the features in your specification expose information about the underlying platform to origins?

The answer is probably "no", but it's worth mentioning that `getSupportedZoomLevels()` exposes the supported zoom-levels on the platform. User agents are encouraged to ensure the result is not dependent on the OS or the user's configuration of the user agent; that is, for a given browser version, the result should be the same for all users on any machine.

### 2.7. Does this specification allow an origin to send data to the underlying platform?

The answer is "no", but it's worth mentioning that `increaseZoomLevel()`, `decreaseZoomLevel()` and `resetZoomLevel()` allow applications to request that the user agent change zoom levels on specific tabs.

### 2.8. Do features in this specification enable access to device sensors?

No.

### 2.9. Do features in this specification enable new script execution/loading mechanisms?

No.

### 2.10. Do features in this specification allow an origin to access other devices?

No.

### 2.11. Do features in this specification allow an origin some measure of control over a user agent’s native UI?

Yes, in a limited way - the zoom-level of captured tabs can be changed. Naturally, this is reflected in the user agent's native UX that informs the user of a tab's zoom-level. This is limited so it only happens in response to direct interaction by the user with the capturing Web application.

### 2.12 What temporary identifiers do the features in this specification create or expose to the web?

None.

### 2.13. How does this specification distinguish between behavior in first-party and third-party contexts?

This feature does not distinguish first-party and third-party contexts.

### 2.14. How do the features in this specification work in the context of a browser’s Private Browsing or Incognito mode?

Not applicable.


### 2.15. Does this specification have both "Security Considerations" and "Privacy Considerations" sections?

Yes.

### 2.16. Do features in your specification enable origins to downgrade default security protections?

No.

### 2.17. How does your feature handle non-"fully active" documents?

This feature only works for documents which use pre-existing mechanisms to initiate tab-capture. A non-"fully active" document will have this capture-session interrupted, thereby also terminating the use of this feature.

### 2.18. What should this questionnaire have asked?

N/A
