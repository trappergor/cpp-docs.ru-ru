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
ms.openlocfilehash: 3ae69e26077692188b8e013e949592df26d7701a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46420404"
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
 
[атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)<br/>
[директива #import](../preprocessor/hash-import-directive-cpp.md)