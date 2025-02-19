---
UID: NF:directxmath.XMQuaternionMultiply
title: XMQuaternionMultiply function (directxmath.h)
description: Computes the product of two quaternions.
helpviewer_keywords: ["Use DirectX..XMQuaternionMultiply","XMQuaternionMultiply","XMQuaternionMultiply method [DirectX Math Support APIs]","dxmath.xmquaternionmultiply"]
old-location: dxmath\xmquaternionmultiply.htm
tech.root: dxmath
ms.assetid: M:Microsoft.directx_sdk.quaternion.XMQuaternionMultiply(XMVECTOR,XMVECTOR)
ms.date: 12/05/2018
ms.keywords: Use DirectX..XMQuaternionMultiply, XMQuaternionMultiply, XMQuaternionMultiply method [DirectX Math Support APIs], dxmath.xmquaternionmultiply
req.header: directxmath.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: Use DirectX.
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
req.redist: 
ms.custom: 19H1
f1_keywords:
 - XMQuaternionMultiply
 - directxmath/XMQuaternionMultiply
dev_langs:
 - c++
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - DirectXMath.h
api_name:
 - XMQuaternionMultiply
---

# XMQuaternionMultiply function


## -description

Computes the product of two quaternions.

## -parameters

### -param Q1 [in]

First quaternion.

### -param Q2 [in]

Second quaternion.

## -returns

Returns the product of two quaternions as <i>Q2</i>*<i>Q1</i>.

## -remarks

The DirectXMath quaternion functions use an XMVECTOR 4-vector to represent quaternions, 
    where the X, Y, and Z components are the vector part and the W component is the scalar part.

The result represents the rotation Q1 followed by the rotation Q2 to be consistent with XMMatrixMulplity 
    concatenation since this function is typically used to concatenate quaternions that represent rotations (i.e. it returns Q2*Q1).

This function computes the equivalent to the following pseduo-code:


```

XMVECTOR Result;
Result.x = (Q2.w * Q1.x) + (Q2.x * Q1.w) + (Q2.y * Q1.z) - (Q2.z * Q1.y);
Result.y = (Q2.w * Q1.y) - (Q2.x * Q1.z) + (Q2.y * Q1.w) + (Q2.z * Q1.x);
Result.z = (Q2.w * Q1.z) + (Q2.x * Q1.y) - (Q2.y * Q1.x) + (Q2.z * Q1.w);
Result.w = (Q2.w * Q1.w) - (Q2.x * Q1.x) - (Q2.y * Q1.y) - (Q2.z * Q1.z);
return Result;
    
```


<h3><a id="Platform_Requirements"></a><a id="platform_requirements"></a><a id="PLATFORM_REQUIREMENTS"></a>Platform Requirements</h3>
Microsoft Visual Studio 2010 or Microsoft Visual Studio 2012 with the Windows SDK for Windows 8. Supported for Win32 desktop apps, Windows Store apps, and Windows Phone 8 apps.

## -see-also

<a href="/windows/desktop/dxmath/ovw-xnamath-reference-functions-quaternion">DirectXMath Library Quaternion Functions</a>