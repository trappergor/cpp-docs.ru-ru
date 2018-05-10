---
title: rename_namespace | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- rename_namespace
dev_langs:
- C++
helpviewer_keywords:
- rename_namespace attribute
ms.assetid: 45006d2b-36cd-4bec-98b9-3b8ec45299e3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a51114787dde2f858a8409538083282ef292d599
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="renamenamespace"></a>rename_namespace
**Конкретных C++**  
  
 Переименовывает пространство имен, к которому относится содержимое библиотеки типов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
rename_namespace("NewName")  
```  
  
#### <a name="parameters"></a>Параметры  
 `NewName`  
 Новое имя пространства имен.  
  
## <a name="remarks"></a>Примечания  
 Он принимает один аргумент, *NewName*, который задает новое имя для пространства имен.  
  
 Чтобы удалить пространство имен, используйте [no_namespace](../preprocessor/no-namespace.md) атрибутом.  
  
 **КОНЕЦ определенного C++**  
  
## <a name="see-also"></a>См. также  
 [атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)   
 [директива #import](../preprocessor/hash-import-directive-cpp.md)