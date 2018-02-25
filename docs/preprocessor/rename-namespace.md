---
title: "rename_namespace | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- rename_namespace
dev_langs:
- C++
helpviewer_keywords:
- rename_namespace attribute
ms.assetid: 45006d2b-36cd-4bec-98b9-3b8ec45299e3
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 37b2c01479cb489f7ed573f55a48f5807161bf63
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
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