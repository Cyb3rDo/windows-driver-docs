---
Description: 'System-Intercepted Device Messages'
MS-HAID: 'audio.system\_intercepted\_device\_messages'
MSHAttr: 'PreferredLib:/library/windows/hardware'
title: 'System-Intercepted Device Messages'
---

# System-Intercepted Device Messages


## <span id="system_intercepted_device_messages"></span><span id="SYSTEM_INTERCEPTED_DEVICE_MESSAGES"></span>


The following Windows multimedia functions provide a way for callers to pass messages to legacy audio devices:

-   [**waveInMessage**](multimedia.waveinmessage)

-   [**waveOutMessage**](multimedia.waveoutmessage)

-   [**midiInMessage**](multimedia.midiinmessage)

-   [**midiOutMessage**](multimedia.midioutmessage)

-   [**mixerMessage**](multimedia.mixermessage)

-   [**auxOutMessage**](multimedia.auxoutmessage)

Some of these device messages are handled directly by the device driver, and some are handled by the system on behalf of the device.

This section discusses only messages that are intercepted by the system and handled without ever being passed to the device driver. System-intercepted messages can obtain the preferred device for voice communications or general audio usage. In addition, system-intercepted messages can provide the following information about a particular device:

-   **The device interface name**

    For information about device interface names, see [Introduction to Device Interfaces](devinst.overview_of_device_interface_classes).

-   **The device's Plug and Play devnode number**

    For information about devnodes, see [Device Tree](kernel.device_tree).

-   **Whether the device can be used by a mapper**

    A mapper selects an appropriate device by mapping an application's requirements to one of the available devices in the system. For more information about mappers, see the Microsoft Windows SDK documentation.

For information about other types of device messages, see the Windows SDK documentation.

An *Xxx*Message function has the following syntax:

```
DWORD XxxMessage(
<device ID>,
    UINT  uMsg,
    DWORD_PTR  dwParam1,
    DWORD_PTR  dwParam2
    );
```

The first parameter is a device ID. The [**auxOutMessage**](multimedia.auxoutmessage) function definition specifies this parameter to be of type UINT, as expected. However, in the case of [**waveInMessage**](multimedia.waveinmessage), [**waveOutMessage**](multimedia.waveoutmessage), [**midiInMessage**](multimedia.midiinmessage), [**midiOutMessage**](multimedia.midioutmessage), or [**mixerMessage**](multimedia.mixermessage), the caller must cast the device ID to handle type HWAVEIN, HWAVEOUT, HMIDIIN, HMIDIOUT, or HMIXER, respectively. Note that if the caller supplies a valid handle instead of a device ID for this parameter, the function fails and returns error code MMSYSERR\_NOSUPPORT.

The *uMsg* parameter specifies a message value (for example, [**DRV\_QUERYDEVICEINTERFACE**](audio.drv_querydeviceinterface)). For a list of driver-specific messages, see header file Mmddk.h.

The meaning of parameters *dwParam1* and *dwParam2* depends on the message. For example, a particular message might require that *dwParam1* be a ULONG value; the caller must cast this value to type DWORD\_PTR to satisfy the function definition.

The function returns MMERR\_NOERROR if the call succeeds, or an error status code if it does not.

For more information about the *Xxx*Message functions, see the Windows SDK documentation.

Header file Mmddk.h defines the following system-intercepted device messages:

[**DRV\_QUERYDEVICEINTERFACE**](audio.drv_querydeviceinterface)

For more information, see [Obtaining a Device Interface Name](obtaining-a-device-interface-name.md).

[**DRV\_QUERYDEVICEINTERFACESIZE**](audio.drv_querydeviceinterfacesize)

For more information, see **Obtaining a Device Interface Name**.

[**DRV\_QUERYDEVNODE**](audio.drv_querydevnode)

Queries for a device's devnode number.

[**DRV\_QUERYMAPPABLE**](audio.drv_querymappable)

Queries whether a device can be used by a mapper.

[**DRVM\_MAPPER\_CONSOLEVOICECOM\_GET**](audio.drvm_mapper_consolevoicecom_get)

For more information, see [Preferred Voice-Communications Device ID](preferred-voice-communications-device-id.md).

[**DRVM\_MAPPER\_PREFERRED\_GET**](audio.drvm_mapper_preferred_get)

For more information, see [Accessing the Preferred Device ID](accessing-the-preferred-device-id.md).

 

 


--------------------
[Send comments about this topic to Microsoft](mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback%20[audio\audio]:%20System-Intercepted%20Device%20Messages%20%20RELEASE:%20%287/14/2016%29&body=%0A%0APRIVACY%20STATEMENT%0A%0AWe%20use%20your%20feedback%20to%20improve%20the%20documentation.%20We%20don't%20use%20your%20email%20address%20for%20any%20other%20purpose,%20and%20we'll%20remove%20your%20email%20address%20from%20our%20system%20after%20the%20issue%20that%20you're%20reporting%20is%20fixed.%20While%20we're%20working%20to%20fix%20this%20issue,%20we%20might%20send%20you%20an%20email%20message%20to%20ask%20for%20more%20info.%20Later,%20we%20might%20also%20send%20you%20an%20email%20message%20to%20let%20you%20know%20that%20we've%20addressed%20your%20feedback.%0A%0AFor%20more%20info%20about%20Microsoft's%20privacy%20policy,%20see%20http://privacy.microsoft.com/en-us/default.aspx. "Send comments about this topic to Microsoft")

