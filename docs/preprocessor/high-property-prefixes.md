---
title: high_property_prefixes | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- high_property_prefixes
dev_langs:
- C++
helpviewer_keywords:
- high_property_prefixes attribute
ms.assetid: 91c6cc2b-19b6-4aba-8831-d9e5cccb58b5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2ce21958dbb928a29debe21fb7cfaed4b9036141
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/10/2018
ms.locfileid: "42539678"
---
# <a name="highpropertyprefixes"></a>high_property_prefixes
**Конкретных C++**  
  
Задает другие префиксы для трех методов свойств.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
high_property_prefixes("GetPrefix","PutPrefix","PutRefPrefix")  
```  
  
### <a name="parameters"></a>Параметры  
*GetPrefix*  
Префикс, используемый для `propget` методы.  
  
*PutPrefix*  
Префикс, используемый для `propput` методы.  
  
*PutRefPrefix*  
Префикс, используемый для `propputref` методы.  
  
## <a name="remarks"></a>Примечания  
 
По умолчанию высокоуровневые обработки ошибок `propget`, `propput`, и `propputref` методы предоставляются функциями-членами, префиксы `Get`, `Put`, и `PutRef`, соответственно.  
  
**КОНЕЦ конкретных C++**  
  
## <a name="see-also"></a>См. также  
 
[атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)   
[директива #import](../preprocessor/hash-import-directive-cpp.md)