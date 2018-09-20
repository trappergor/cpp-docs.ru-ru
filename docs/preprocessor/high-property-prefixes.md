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
ms.openlocfilehash: 6f188cd833551542e636e764e76784635ae2ccf2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46422770"
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
 
[атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)<br/>
[директива #import](../preprocessor/hash-import-directive-cpp.md)