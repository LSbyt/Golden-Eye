# GoldenEye

<img src='./logo.svg' width='264'/>

## Quick guide

#### Add dependency

```gradle
implementation 'co.infinum:goldeneye:1.1.2'
```

#### Initialize

```kotlin
val goldenEye = GoldenEye.Builder(activity).build()
```

#### Open camera

```kotlin
if (ContextCompat.checkSelfPermission(context, Manifest.permission.CAMERA)
    == PackageManager.PERMISSION_GRANTED
    ) {
  /* Find back camera */
  val backCamera = goldenEye.availableCameras.find { it.facing == Facing.BACK }
  /* Open back camera */
  goldenEye.open(textureView, backCamera, initCallback)
}
```

#### Take picture

```kotlin
goldenEye.takePicture(pictureCallback)
```

#### Record video

```kotlin
goldenEye.startRecording(file, videoCallback)
/* Somewhere later */
goldenEye.stopRecording()
```
