# Build signed APK

Build a signed APK of your Android application

## Inputs

| Name | Description | Required | Default |
| --- | --- | --- | --- |
| keystore_b64 or keystore_file | Base64 encoded keystore or path to the keystore file | true | |
| keystore_password | Password of the keystore | true | |
| key_alias | Alias of the key | true |  |
| key_password | Password of the key | true | |
| java_version | Java version to use | false | 17 |
| java_distribution | Java distribution to use | false | zulu |
| gradlew_dir | Directory where the gradlew file is located | false | . |

If both `keystore_b64` and `keystore_file` are defined, only `keystore_b64` will be used. At least one of them must be defined.

## Example

```yaml
- name: Build Signed APK
  uses: TeamNecta/build-signed-apk@main
  with:
    keystore_b64: ${{ secrets.keystore }}
    keystore_password: ${{ secrets.keystore_password }}
    key_alias: ${{ secrets.key_alias }}
    key_password: ${{ secrets.key_password }}
```

## Get your APK

The APK is built at the default location, which is: `app/build/outputs/apk/release/app-release.apk`. Feel free to do whatever you want with this apk now, like creating a release with it or putting it as an artifact of the release
