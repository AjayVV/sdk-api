---
UID: NF:gdiplustypes.RectF.Equals
title: RectF::Equals (gdiplustypes.h)
description: The RectF::Equals method determines whether two rectangles are the same.helpviewer_keywords: ["Equals","Equals method [GDI+]","Equals method [GDI+]","RectF class","RectF class [GDI+]","Equals method","RectF.Equals","RectF::Equals","_gdiplus_CLASS_RectF_Equals_rect_","gdiplus._gdiplus_CLASS_RectF_Equals_rect_"]
old-location: gdiplus\_gdiplus_CLASS_RectF_Equals_rect_.htm
tech.root: gdiplus
ms.assetid: VS|gdicpp|~\gdiplus\gdiplusreference\classes\rectfclass\rectfmethods\equals_30rect.htm
ms.date: 12/05/2018
ms.keywords: Equals, Equals method [GDI+], Equals method [GDI+],RectF class, RectF class [GDI+],Equals method, RectF.Equals, RectF::Equals, _gdiplus_CLASS_RectF_Equals_rect_, gdiplus._gdiplus_CLASS_RectF_Equals_rect_
f1_keywords:
- gdiplustypes/RectF.Equals
dev_langs:
- c++
req.header: gdiplustypes.h
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
- COM
api_location:
- Gdiplus.dll
api_name:
- RectF.Equals
targetos: Windows
req.typenames: 
req.redist: 
req.product: GDI+ 1.0
ms.custom: 19H1
---

# RectF::Equals


## -description


The <b>RectF::Equals</b> method determines whether two rectangles are the same. 


## -parameters




### -param rect [in]

Type: <b>const RectF&amp;</b>

Reference to a rectangle to compare to this rectangle. 


## -returns



Type: <b>BOOL</b>

If the rectangles are the same, this method returns <b>TRUE</b>; otherwise, it returns <b>FALSE</b>.




## -remarks



Two rectangles are the same if their 
				<b>X</b>, 
				<b>Y</b>, 
				<b>Width</b>, and 
				<b>Height</b> data members are the same.


#### Examples



The following example creates two 
						<a href="https://docs.microsoft.com/windows/desktop/api/gdiplustypes/nl-gdiplustypes-rectf">RectF</a> objects, moves the second 
						<b>RectF</b> object horizontally by a specified value, and then determines whether the two 
						<b>RectF</b> objects are the same.


```cpp
VOID Example_Equals(HDC hdc)
{
   Graphics graphics(hdc);

   RectF rect1(50, 50, 200, 100);
   RectF rect2(20, 50, 200, 100);

   rect2.Offset(30, 0);

   if(rect2.Equals(rect1))
   {
      // The two rectangles are the same.
   }
}
```





## -see-also




<a href="https://docs.microsoft.com/windows/desktop/gdiplus/-gdiplus-pens-lines-and-rectangles-about">Pens, Lines, and Rectangles</a>



<a href="https://docs.microsoft.com/windows/desktop/api/gdiplustypes/nl-gdiplustypes-rect">Rect</a>



<a href="https://docs.microsoft.com/windows/desktop/api/gdiplustypes/nl-gdiplustypes-rectf">RectF</a>



<a href="https://docs.microsoft.com/windows/desktop/gdiplus/-gdiplus-using-a-pen-to-draw-lines-and-rectangles-use">Using a Pen to Draw Lines and Rectangles</a>
 

 

