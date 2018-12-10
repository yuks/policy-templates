**IMPORTANT**: These files are in active development along with the policies in Firefox. To get the policy information that corresponds to a specific release, go to https://github.com/mozilla/policy-templates/releases.

Starting with Firefox 64 and Firefox ESR 60.4, Firefox supports configuration files on macOS.

An example plist file with all options is available here:

https://github.com/mozilla/policy-templates/blob/master/mac/org.mozilla.firefox.plist

If you want to set specific options from the command line, we also provide flattened shortcuts to any item that is nested in the plist file.

For example, this policy:
```
{
  "policies": {
    "Homepage": {
      "URL": "http://example.com/"
    }
  }
}
```
which would be set in the plist file like this:
```
	<key>Homepage</key>
	<dict>
		<key>URL</key>
		<string>http://example.com</string>
    </dict>
```
can be set via the command line like this:
```
defaults write org.mozilla.firefox Homepage__URL -string "http://example.com"
```
Before any command line policies will work, you need to enable policies like this:
```
defaults write org.mozilla.firefox EnterprisePoliciesEnabled -bool TRUE
```