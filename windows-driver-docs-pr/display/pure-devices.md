---
title: Pure Devices
description: Pure Devices
ms.assetid: 6ad3412c-fd80-41c0-9abc-117aacc5ddae
keywords: ["DirectX 8.0 release notes WDK Windows 2000 display , pure devices", "pure devices WDK DirectX 8.0"]
---

# Pure Devices


## <span id="ddk_pure_devices_gg"></span><span id="DDK_PURE_DEVICES_GG"></span>


DirectX 8.0 introduces the concept of a "pure" device. When using a pure device the runtime does not track state or state blocks or perform any software vertex processing on behalf of the hardware. Furthermore, the application cannot query back state from the runtime. The lack of state tracking, particularly when state blocks are being used, can result in a significant performance boost for the application.

Only vertex processing directly supported by the hardware is available to the application when using a pure device. For example, for cards that do not support hardware transform and lighting, only pretransformed vertices can be passed to Direct3D. Furthermore, the API functions **SetClipStatus**, **GetClipStatus** and **ProcessVertices** cannot be used with the pure device.

In order to use a pure device the application must request it with the device creation flag D3DCREATE\_PUREDEVICE and the driver must report its ability to act as a pure device.

 

 

[Send comments about this topic to Microsoft](mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback%20[display\display]:%20Pure%20Devices%20%20RELEASE:%20%282/10/2017%29&body=%0A%0APRIVACY%20STATEMENT%0A%0AWe%20use%20your%20feedback%20to%20improve%20the%20documentation.%20We%20don't%20use%20your%20email%20address%20for%20any%20other%20purpose,%20and%20we'll%20remove%20your%20email%20address%20from%20our%20system%20after%20the%20issue%20that%20you're%20reporting%20is%20fixed.%20While%20we're%20working%20to%20fix%20this%20issue,%20we%20might%20send%20you%20an%20email%20message%20to%20ask%20for%20more%20info.%20Later,%20we%20might%20also%20send%20you%20an%20email%20message%20to%20let%20you%20know%20that%20we've%20addressed%20your%20feedback.%0A%0AFor%20more%20info%20about%20Microsoft's%20privacy%20policy,%20see%20http://privacy.microsoft.com/default.aspx. "Send comments about this topic to Microsoft")



