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
ms.openlocfilehash: f5bd922089bcf189c403a97679a593a985603a12
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46446261"
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
 
[атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)<br/>
[директива #import](../preprocessor/hash-import-directive-cpp.md)