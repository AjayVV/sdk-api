---
UID: NN:emptyvc.IEmptyVolumeCache
title: IEmptyVolumeCache (emptyvc.h)
description: Used by the disk cleanup manager to communicate with a disk cleanup handler. Exposes methods that enable the manager to request information from a handler, and notify it of events such as the start of a scan or purge.helpviewer_keywords: ["IEmptyVolumeCache","IEmptyVolumeCache interface [Legacy Windows Environment Features]","IEmptyVolumeCache interface [Legacy Windows Environment Features]","described","_win32_IEmptyVolumeCache","emptyvc/IEmptyVolumeCache","lwef.iemptyvolumecache","shell.iemptyvolumecache"]
old-location: lwef\iemptyvolumecache.htm
tech.root: lwef
ms.assetid: ba3797c2-f82c-4721-b72d-8552683a10d2
ms.date: 12/05/2018
ms.keywords: IEmptyVolumeCache, IEmptyVolumeCache interface [Legacy Windows Environment Features], IEmptyVolumeCache interface [Legacy Windows Environment Features],described, _win32_IEmptyVolumeCache, emptyvc/IEmptyVolumeCache, lwef.iemptyvolumecache, shell.iemptyvolumecache
f1_keywords:
- emptyvc/IEmptyVolumeCache
dev_langs:
- c++
req.header: emptyvc.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 2000 Professional, Windows XP [desktop apps only]
req.target-min-winversvr: Windows Server 2003 [desktop apps only]
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: Shell32.dll (version 5.0 or later)
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- Shell32.dll
api_name:
- IEmptyVolumeCache
targetos: Windows
req.typenames: 
req.redist: 
ms.custom: 19H1
---

# IEmptyVolumeCache interface


## -description


Used by the disk cleanup manager to communicate with a disk cleanup handler. Exposes methods that enable the manager to request information from a handler, and notify it of events such as the start of a scan or purge.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IEmptyVolumeCache</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IEmptyVolumeCache</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IEmptyVolumeCache</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows/desktop/api/emptyvc/nf-emptyvc-iemptyvolumecache-deactivate">Deactivate</a>
</td>
<td align="left" width="63%">
Notifies the handler that the disk cleanup manager is shutting down. 

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows/desktop/api/emptyvc/nf-emptyvc-iemptyvolumecache-getspaceused">GetSpaceUsed</a>
</td>
<td align="left" width="63%">
Requests the amount of disk space that the disk cleanup handler can free.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows/desktop/api/emptyvc/nf-emptyvc-iemptyvolumecache-initialize">Initialize</a>
</td>
<td align="left" width="63%">
Initializes the disk cleanup handler, based on the information stored under the specified registry key.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows/desktop/api/emptyvc/nf-emptyvc-iemptyvolumecache-purge">Purge</a>
</td>
<td align="left" width="63%">
Notifies the handler to start deleting its unneeded files.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows/desktop/api/emptyvc/nf-emptyvc-iemptyvolumecache-showproperties">ShowProperties</a>
</td>
<td align="left" width="63%">
Notifies the handler to display its UI. 

</td>
</tr>
</table> 


## -remarks



This interface must be implemented by disk cleanup handlers running on Windows 98. Handlers running on Windows 2000 should also expose <a href="https://docs.microsoft.com/windows/desktop/api/emptyvc/nn-emptyvc-iemptyvolumecache2">IEmptyVolumeCache2</a>.




## -see-also




<a href="https://docs.microsoft.com/windows/desktop/api/emptyvc/nn-emptyvc-iemptyvolumecachecallback">IEmptyVolumeCacheCallBack</a>
 

 

