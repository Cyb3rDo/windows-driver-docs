---
title: WIA\_DPC\_PICTURES\_REMAINING
description: The WIA\_DPC\_PICTURES\_REMAINING property contains the number of pictures that a user can take by using a camera device, given the current property settings. The WIA minidriver creates and maintains this property.
ms.assetid: ac6cd3e0-c6fe-4783-8094-67083e308308
keywords: ["WIA_DPC_PICTURES_REMAINING Imaging Devices"]
topic_type:
- apiref
api_name:
- WIA_DPC_PICTURES_REMAINING
api_location:
- Wiadef.h
api_type:
- HeaderDef
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.topic: article
ms.prod: windows-hardware
ms.technology: windows-devices
---

# WIA\_DPC\_PICTURES\_REMAINING


The WIA\_DPC\_PICTURES\_REMAINING property contains the number of pictures that a user can take by using a camera device, given the current property settings. The WIA minidriver creates and maintains this property.

## <span id="ddk_wia_dpc_pictures_remaining_si"></span><span id="DDK_WIA_DPC_PICTURES_REMAINING_SI"></span>


Property Type: VT\_I4

Valid Values: WIA\_PROP\_NONE

Access Rights: Read-only

Remarks
-------

If the WIA\_DPC\_PICTURES\_REMAINING property settings change and the changes affect the size of the images that the camera device produces, the WIA minidriver should update the number of remaining pictures.

Requirements
------------

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Version</p></td>
<td><p>Obsolete in Windows Vista and later operating systems and should no longer be used. However, this property is still defined in Windows Vista for compatibility with applications and devices designed for Windows Server 2003, Windows XP, and previous versions of Windows.</p></td>
</tr>
<tr class="even">
<td><p>Header</p></td>
<td>Wiadef.h (include Wiadef.h)</td>
</tr>
</tbody>
</table>

 

 

[Send comments about this topic to Microsoft](mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback%20%5Bimage\image%5D:%20WIA_DPC_PICTURES_REMAINING%20%20RELEASE:%20%2811/13/2017%29&body=%0A%0APRIVACY%20STATEMENT%0A%0AWe%20use%20your%20feedback%20to%20improve%20the%20documentation.%20We%20don't%20use%20your%20email%20address%20for%20any%20other%20purpose,%20and%20we'll%20remove%20your%20email%20address%20from%20our%20system%20after%20the%20issue%20that%20you're%20reporting%20is%20fixed.%20While%20we're%20working%20to%20fix%20this%20issue,%20we%20might%20send%20you%20an%20email%20message%20to%20ask%20for%20more%20info.%20Later,%20we%20might%20also%20send%20you%20an%20email%20message%20to%20let%20you%20know%20that%20we've%20addressed%20your%20feedback.%0A%0AFor%20more%20info%20about%20Microsoft's%20privacy%20policy,%20see%20http://privacy.microsoft.com/default.aspx. "Send comments about this topic to Microsoft")




