---
UID: NF:gdiplusinit.GdiplusStartup
title: GdiplusStartup function (gdiplusinit.h)
description: The GdiplusStartup function initializes Windows GDI+. Call GdiplusStartup before making any other GDI+ calls, and call GdiplusShutdown when you have finished using GDI+.helpviewer_keywords: ["GdiplusStartup","GdiplusStartup function [GDI+]","_gdiplus_FUNC_GdiplusStartup_token_input_output_","gdiplus._gdiplus_FUNC_GdiplusStartup_token_input_output_","gdiplusinit/GdiplusStartup"]
old-location: gdiplus\_gdiplus_FUNC_GdiplusStartup_token_input_output_.htm
tech.root: gdiplus
ms.assetid: VS|gdicpp|~\gdiplus\gdiplusreference\functions\gdiplusstartup.htm
ms.date: 12/05/2018
ms.keywords: GdiplusStartup, GdiplusStartup function [GDI+], _gdiplus_FUNC_GdiplusStartup_token_input_output_, gdiplus._gdiplus_FUNC_GdiplusStartup_token_input_output_, gdiplusinit/GdiplusStartup
f1_keywords:
- gdiplusinit/GdiplusStartup
dev_langs:
- c++
req.header: gdiplusinit.h
req.include-header: Gdiplus.h
req.target-type: Windows
req.target-min-winverclnt: Windows XP, Windows 2000 Professional [desktop apps only]
req.target-min-winversvr: Windows 2000 Server [desktop apps only]
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Gdiplus.lib
req.dll: Gdiplus.dll
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Gdiplus.dll
api_name:
- GdiplusStartup
targetos: Windows
req.typenames: 
req.redist: 
req.product: GDI+ 1.0
ms.custom: 19H1
---

# GdiplusStartup function


## -description


The <b>GdiplusStartup</b> function initializes Windows GDI+. Call <b>GdiplusStartup</b> before making any other GDI+ calls, and call <a href="https://docs.microsoft.com/windows/desktop/api/gdiplusinit/nf-gdiplusinit-gdiplusshutdown">GdiplusShutdown</a> when you have finished using GDI+.


## -parameters




### -param token [out]

Type: <b>ULONG_PTR token*</b>

Pointer to a 
					<b>ULONG_PTR</b> that receives a token. Pass the token to <a href="https://docs.microsoft.com/windows/desktop/api/gdiplusinit/nf-gdiplusinit-gdiplusshutdown">GdiplusShutdown</a> when you have finished using GDI+. 


### -param input [in]

Type: <b>const <a href="https://docs.microsoft.com/windows/desktop/api/gdiplusinit/ns-gdiplusinit-gdiplusstartupinput">GdiplusStartupInput</a>*</b>

Pointer to a <a href="https://docs.microsoft.com/windows/desktop/api/gdiplusinit/ns-gdiplusinit-gdiplusstartupinput">GdiplusStartupInput</a> structure that contains the GDI+ version, a pointer to a debug callback function, a Boolean value that specifies whether to suppress the background thread, and a Boolean value that specifies whether to suppress external image codecs. 


### -param output [out]

Type: <b><a href="https://docs.microsoft.com/windows/desktop/api/gdiplusinit/ns-gdiplusinit-gdiplusstartupoutput">GdiplusStartupOutput</a>*</b>

Pointer to a <a href="https://docs.microsoft.com/windows/desktop/api/gdiplusinit/ns-gdiplusinit-gdiplusstartupoutput">GdiplusStartupOutput</a> structure that receives a pointer to a notification hook function and a pointer to a notification unhook function. If the 
					<b>SuppressBackgroundThread</b> data member of the 
					<i>input</i> parameter is <b>FALSE</b>, then this parameter can be <b>NULL</b>. 


## -returns



Type: <b><a href="https://docs.microsoft.com/windows/desktop/api/gdiplustypes/ne-gdiplustypes-status">Status</a></b>

If the function succeeds, it returns <b>Ok</b>, which is an element of the 
						<a href="https://docs.microsoft.com/windows/desktop/api/gdiplustypes/ne-gdiplustypes-status">Status</a> enumeration.

If the function fails, it returns one of the other elements of the 
						<a href="https://docs.microsoft.com/windows/desktop/api/gdiplustypes/ne-gdiplustypes-status">Status</a> enumeration.




## -remarks



You must call <b>GdiplusStartup</b> before you create any GDI+ objects, and you must delete all of your GDI+ objects (or have them go out of scope) before you call <a href="https://docs.microsoft.com/windows/desktop/api/gdiplusinit/nf-gdiplusinit-gdiplusshutdown">GdiplusShutdown</a>.

You can call <b>GdiplusStartup</b> on one thread and call <a href="https://docs.microsoft.com/windows/desktop/api/gdiplusinit/nf-gdiplusinit-gdiplusshutdown">GdiplusShutdown</a> on another thread as long as you delete all of your GDI+ objects (or have them go out of scope) before you call <b>GdiplusShutdown</b>.

Do not call <b>GdiplusStartup</b> or <a href="https://docs.microsoft.com/windows/desktop/api/gdiplusinit/nf-gdiplusinit-gdiplusshutdown">GdiplusShutdown</a> in 
				<a href="https://docs.microsoft.com/windows/desktop/Dlls/dllmain">DllMain</a> or in any function that is called by DllMain. If you want to create a DLL that uses GDI+, you should use one of the following techniques to initialize GDI+:

<ul>
<li>Require your clients to call <b>GdiplusStartup</b> before they call the functions in your DLL and to call <a href="https://docs.microsoft.com/windows/desktop/api/gdiplusinit/nf-gdiplusinit-gdiplusshutdown">GdiplusShutdown</a> when they have finished using your DLL. </li>
<li>Export your own startup function that calls <b>GdiplusStartup</b> and your own shutdown function that calls <a href="https://docs.microsoft.com/windows/desktop/api/gdiplusinit/nf-gdiplusinit-gdiplusshutdown">GdiplusShutdown</a>. Require your clients to call your startup function before they call other functions in your DLL and to call your shutdown function when they have finished using your DLL. </li>
<li>Call <b>GdiplusStartup</b> and <a href="https://docs.microsoft.com/windows/desktop/api/gdiplusinit/nf-gdiplusinit-gdiplusshutdown">GdiplusShutdown</a> in each of your functions that make GDI+ calls. </li>
</ul>
<div class="alert"><b>Warning</b>  For info about how to use dynamic data exchange (DDE) with GDI+, see <a href="https://msdn.microsoft.com/library/001tckck.aspx">Special CWinApp Services</a>.</div>
<div> </div>

#### Examples



For an example of calling <b>GdiplusStartup</b> and <a href="https://docs.microsoft.com/windows/desktop/api/gdiplusinit/nf-gdiplusinit-gdiplusshutdown">GdiplusShutdown</a> in a Windows application, see <a href="https://docs.microsoft.com/windows/desktop/gdiplus/-gdiplus-getting-started-use">Getting Started</a>.

The following console application uses a GDI+<a href="https://docs.microsoft.com/windows/desktop/api/gdiplusheaders/nl-gdiplusheaders-image">Image</a> object to retrieve the width and height of a JPEG image. The code calls <b>GdiplusStartup</b> before creating the 
						<b>Image</b> object and calls <a href="https://docs.microsoft.com/windows/desktop/api/gdiplusinit/nf-gdiplusinit-gdiplusshutdown">GdiplusShutdown</a> before terminating. Note that the 
						<b>Image</b> object is deleted before the call to <b>GdiplusShutdown</b>.

In the following code, the variable 
						<i>gdiplusStartupInput</i> is initialized by the default constructor of the <a href="https://docs.microsoft.com/windows/desktop/api/gdiplusinit/ns-gdiplusinit-gdiplusstartupinput">GdiplusStartupInput</a> structure. The default constructor sets the data members of the structure to the following values: 

<ul>
<li><b>GdiplusVersion</b> = 1 </li>
<li><b>DebugEventCallback</b> = <b>NULL</b></li>
<li><b>SuppressBackgroundThread</b> = <b>FALSE</b></li>
<li><b>SuppressExternalCodecs</b> = <b>FALSE</b></li>
</ul>

```cpp
#include <windows.h>
#include <gdiplus.h>
#include <stdio.h>
using namespace Gdiplus;

INT main()
{
   GdiplusStartupInput gdiplusStartupInput;
   ULONG_PTR gdiplusToken;
   GdiplusStartup(&gdiplusToken, &gdiplusStartupInput, NULL);

   Image* image = new Image(L"FakePhoto.jpg");
   printf("The width of the image is %u.\n", image->GetWidth());
   printf("The height of the image is %u.\n", image->GetHeight()); 

   delete image;
   GdiplusShutdown(gdiplusToken);
   return 0;
}
```





## -see-also




<a href="https://docs.microsoft.com/windows/desktop/api/gdiplusinit/nf-gdiplusinit-gdiplusshutdown">GdiplusShutdown</a>



<a href="https://docs.microsoft.com/windows/desktop/api/gdiplusinit/ns-gdiplusinit-gdiplusstartupinput">GdiplusStartupInput</a>



<a href="https://docs.microsoft.com/windows/desktop/api/gdiplusinit/ns-gdiplusinit-gdiplusstartupoutput">GdiplusStartupOutput</a>



<a href="https://docs.microsoft.com/windows/desktop/gdiplus/-gdiplus-getting-started-use">Getting Started</a>
 

 

