---
title: high_property_prefixes | Документы Microsoft
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
ms.openlocfilehash: 7269301fed3892fbf4b7cf6427bacb82d9712ef7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="highpropertyprefixes"></a>high_property_prefixes
**Конкретных C++**  
  
 Задает другие префиксы для трех методов свойств.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
high_property_prefixes("GetPrefix","PutPrefix","PutRefPrefix")  
```  
  
#### <a name="parameters"></a>Параметры  
 `GetPrefix`  
 Префикс, используемый для **propget** методы.  
  
 `PutPrefix`  
 Префикс, используемый для **propput** методы.  
  
 `PutRefPrefix`  
 Префикс, используемый для **propputref** методы.  
  
## <a name="remarks"></a>Примечания  
 По умолчанию высокоуровневые способы обработки ошибок **propget**, **propput**, и **propputref** методы предоставляются функциями-членами, именам которых предшествуют префиксы **получить** , `Put`, и **PutRef**соответственно.  
  
 **КОНЕЦ определенного C++**  
  
## <a name="see-also"></a>См. также  
 [атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)   
 [директива #import](../preprocessor/hash-import-directive-cpp.md)