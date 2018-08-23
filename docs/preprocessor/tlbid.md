---
title: TLBID | Документация Майкрософт
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
ms.openlocfilehash: 1ec0150e63209728cf2f02c854fe03702b8a45b4
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/10/2018
ms.locfileid: "42544498"
---
# <a name="tlbid"></a>tlbid
**Конкретных C++**  
  
Позволяет загружать библиотеки, отличные от основной библиотеки типов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
tlbid(number)  
```  
  
### <a name="parameters"></a>Параметры  
*номер*  
Номер библиотеки типов в файле с именем `filename`.  
  
## <a name="remarks"></a>Примечания  
 
Если несколько библиотек типов встроены в одной библиотеки DLL, можно загружать библиотеки, отличные от основной библиотеки типов с помощью **tlbid**.  
  
Пример:  
  
```  
#import <MyResource.dll> tlbid(2)  
```  
  
эквивалентно выражению:  
  
```  
LoadTypeLib("MyResource.dll\\2");  
```  
  
**КОНЕЦ конкретных C++**  
  
## <a name="see-also"></a>См. также  
 
[атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)   
[директива #import](../preprocessor/hash-import-directive-cpp.md)