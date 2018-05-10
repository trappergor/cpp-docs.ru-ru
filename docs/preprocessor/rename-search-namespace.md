---
title: rename_search_namespace | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- rename_search_namespace
dev_langs:
- C++
helpviewer_keywords:
- rename_search_namespace attribute
ms.assetid: 47c9d7fd-59dc-4c62-87a1-9011a0040167
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 367294991b9cbb07ee7c852d757842a20c51cc30
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="renamesearchnamespace"></a>rename_search_namespace
**Конкретных C++**  
  
 Имеет ту же функциональность, что [rename_namespace](../preprocessor/rename-namespace.md) атрибута, но используется для библиотек типов, которые можно использовать директиву #import с [auto_search](../preprocessor/auto-search.md) атрибута.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
rename_search_namespace("NewName")  
```  
  
#### <a name="parameters"></a>Параметры  
 `NewName`  
 Новое имя пространства имен.  
  
## <a name="remarks"></a>Примечания  
 **КОНЕЦ определенного C++**  
  
## <a name="see-also"></a>См. также  
 [атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)   
 [директива #import](../preprocessor/hash-import-directive-cpp.md)