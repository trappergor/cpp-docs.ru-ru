---
title: raw_property_prefixes | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- raw_property_prefixes
dev_langs:
- C++
helpviewer_keywords:
- raw_property_prefixes attribute
ms.assetid: 03a0f48c-c460-4175-a762-9f7f8d84b12f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 423a66b698f4e421ff29e6ac3dfddd11fa11c58f
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/10/2018
ms.locfileid: "42541061"
---
# <a name="rawpropertyprefixes"></a>raw_property_prefixes
**Конкретных C++**  
  
Задает другие префиксы для трех методов свойств.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
raw_property_prefixes("GetPrefix","PutPrefix","PutRefPrefix")  
```  
  
### <a name="parameters"></a>Параметры  
*GetPrefix*  
Префикс, используемый для `propget` методы.  
  
*PutPrefix*  
Префикс, используемый для `propput` методы.  
  
*PutRefPrefix*  
Префикс, используемый для `propputref` методы.  
  
## <a name="remarks"></a>Примечания  
 
По умолчанию низкоуровневые `propget`, `propput`, и `propputref` методы предоставляются функциями-членами, именами, содержащими префиксы **get_**, **put_**, и **putref_** соответственно. Эти префиксы совместимы с именами, используемыми в файлах заголовков, которые генерирует MIDL.  
  
**КОНЕЦ конкретных C++**  
  
## <a name="see-also"></a>См. также  
 
[атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)   
[директива #import](../preprocessor/hash-import-directive-cpp.md)