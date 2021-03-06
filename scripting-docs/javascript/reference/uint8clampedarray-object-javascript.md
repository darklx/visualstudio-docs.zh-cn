---
title: "Uint8ClampedArray 对象 (JavaScript) |Microsoft 文档"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 0c5537f7-00b4-487a-8fba-ef032e67e7bd
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 51673eadc8eb905355bf136dc82b2f240462180a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2017
---
# <a name="uint8clampedarray-object-javascript"></a>Uint8ClampedArray 对象 (JavaScript)
8 位无符号整数的类型化数组，其值限制为 0-255。 内容将初始化为 0。 如果无法分配请求数目的字节，则将引发异常。  
  
## <a name="syntax"></a>语法  
  
```  
  
      uint8ClampedArray = new Uint8ClampedArray( length );  
uint8ClampedArray = new Uint8ClampedArray( array );  
uint8ClampedArray = new Uint8ClampedArray( buffer, byteOffset, length);  
```  
  
## <a name="parameters"></a>参数  
 `uint8ClampedArray`  
 必需。 `Uint8ClampedArray` 对象分配到的变量名称。  
  
 `length`  
 可选。 数组中的元素数。  
  
 `array`  
 可选。 该数组中包含的数组（或类型化数组）。 内容将初始化为给定数组或类型化数组的内容，且每个元素均转换为 `Uint8` 类型。  
  
 `buffer`  
 可选。 [ArrayBuffer](../../javascript/reference/arraybuffer-object.md) ，`Uint8ClampedArray`表示。  
  
 `byteOffset`  
 可选。 从应开始 `Uint8ClampedArray` 的缓冲区开始处的偏移量（以字节为单位）。  
  
 `length`  
 可选。 数组中的元素数。  
  
## <a name="remarks"></a>备注  
 存储在 `Uint8ClampedArray` 对象中的值介于 0 和 255 之间。 如果你为某个数组成员设置了负值，该值将设置为 0。 如果你设置的值大于 255，该值将设置为 255。  
  
 中的值`Uint8ClampedArray`对象舍入为最接近的偶数值，这种行为称为银行家舍入。  
  
## <a name="constants"></a>常量  
 下表列出了 `Uint8ClampedArray` 对象的常量。  
  
|常量|描述|  
|--------------|-----------------|  
|[BYTES_PER_ELEMENT 常量](../../javascript/reference/bytes-per-element-constant-uint8clampedarray.md)|数组中每个元素的大小（以字节为单位）。|  
  
## <a name="properties"></a>属性  
 下表列出了 `Uint8ClampedArray` 对象的常量。  
  
|属性|描述|  
|--------------|-----------------|  
|[buffer 属性](../../javascript/reference/buffer-property-uint8clampedarray.md)|只读。 获取[ArrayBuffer](../../javascript/reference/arraybuffer-object.md)此数组引用。|  
|[byteLength 属性](../../javascript/reference/bytelength-property-uint8clampedarray.md)|只读。 此数组开始处的长度其[ArrayBuffer](../../javascript/reference/arraybuffer-object.md)，以字节为单位，如在构造时已固定。|  
|[byteOffset 属性](../../javascript/reference/byteoffset-property-uint8clampedarray.md)|只读。 此数组开始处的偏移量其[ArrayBuffer](../../javascript/reference/arraybuffer-object.md)，以字节为单位，如在构造时已固定。|  
|[length 属性](../../javascript/reference/length-property-uint8clampedarray.md)|数组的长度。|  
  
## <a name="methods"></a>方法  
 下表列出了 `Uint8ClampedArray` 对象的方法。  
  
|方法|描述|  
|------------|-----------------|  
|[set 方法](../../javascript/reference/set-method-uint8clampedarray.md)|设置值或值数组。|  
|[subarray 方法](../../javascript/reference/subarray-method-uint8clampedarray.md)|获取一个新`Uint8ClampedArray`视图[ArrayBuffer](../../javascript/reference/arraybuffer-object.md)存储为此数组，指定子数组的第一个和最后一个元素。|  
  
## <a name="example"></a>示例  
 以下示例演示如何使用 `Uint8ClampedArray` 对象处理从 `XmlHttpRequest` 获取的二进制数据：  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataview = new DataView(buffer);  
            var ints = new Uint8ClampedArray(buffer.byteLength);  
            for (var i = 0; i < ints.length; i++) {  
                ints[i] = dataview.getUint8(i);  
            }  
        alert(ints[10]);  
        }  
    }  
  
```  
  
## <a name="example"></a>示例  
 以下示例演示如何在 `Uint8ClampedArray` 中限制值。  
  
```JavaScript  
var ints = new Uint8ClampedArray(2);  
ints[0] = -1;  // 0 will be assigned.  
ints[1] = 256; // 255 will be assigned.  
  
```  
  
## <a name="example"></a>示例  
 以下示例演示如何在 `Uint8ClampedArray` 中舍入值。  
  
```  
var ints = new Uint8ClampedArray(4);  
ints[0] = 11.3; // 11 will be assigned (same as Int8Array).  
ints[1] = 11.8; // 12 will be assigned (same as Int8Array).  
ints[2] = 10.5; // 10 will be assigned (rounded to the nearest   
                // even value).  
ints[3] = 11.5; // 12 will be assigned (rounded to the nearest   
                // even value).  
  
```  
  
## <a name="requirements"></a>要求  
 [!INCLUDE[jsv11_winonly](../../javascript/reference/includes/jsv11-winonly-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [Uint8Array 对象](../../javascript/reference/uint8array-object.md)   
 [ArrayBuffer 对象](../../javascript/reference/arraybuffer-object.md)
