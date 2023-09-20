# Android

!!! info ""
    :fontawesome-brands-github: Find the [source code on Github](https://github.com/photos-network/android)

The app can be used without any core instance connected with a limited feature set.

### Photos
A grid showing all media items like photos and videos available on the current device merged with items shared remotely when a main core instance is connected. 

### Albums

A list of shared albums either owned or shared by other people on the same instance.

### Folders

Local folders on the device with items even not added to the database or a connected core instance.

### Setup [:fontawesome-solid-link:]("Only when connected to a core instance")

Connect to a core instance by adding the **Host** and a **Client ID** to get access to additional features.

### Share [:fontawesome-solid-link:]("Only when connected to a core instance")

Share albums with friends and family or with the public just with a simple link. If they have an account on the same instance, they will see the albums and items in their app.

## Structure
The app is split by layers for a clean and easy to understand setup.

```shell
core/
├── app/
│   ├── src/main/kotlin/photos/network/
│   ├── main.rs
│   └── lib.rs
├── api/
├── common/
├── database/
│   ├── photos/
│   ├── albums/
│   ├── settings/
│   └── sharing/
├── domain/
├── repository/
├── system/
├── ui/
│   ├── albums/
│   ├── folders/
│   ├── photos/
│   ├── search/
│   ├── settings/
└── settings.gradle.kts
```
