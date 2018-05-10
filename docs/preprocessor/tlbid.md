---
title: TLBID | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- tlbid
dev_langs:
- C++
helpviewer_keywords:
- tlbid attribute
ms.assetid: 54b06785-191b-4e77-a9a5-485f2b4acb09
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9d651546733f42b1a714ac7a39992fa2d392c8fa
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="tlbid"></a>tlbid
**Конкретных C++**  
  
 Позволяет загружать библиотеки, отличные от основной библиотеки типов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
tlbid(number)  
```  
  
#### <a name="parameters"></a>Параметры  
 `number`  
 Номер библиотеки типов в файле с именем `filename`.  
  
## <a name="remarks"></a>Примечания  
 Если в одну библиотеку DLL встроено несколько библиотек типов, с помощью `tlbid` можно загружать библиотеки, отличные от основной библиотеки типов.  
  
 Пример:  
  
```  
#import <MyResource.dll> tlbid(2)  
```  
  
 эквивалентно выражению:  
  
```  
LoadTypeLib("MyResource.dll\\2");  
```  
  
 **КОНЕЦ определенного C++**  
  
## <a name="see-also"></a>См. также  
 [атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)   
 [директива #import](../preprocessor/hash-import-directive-cpp.md)