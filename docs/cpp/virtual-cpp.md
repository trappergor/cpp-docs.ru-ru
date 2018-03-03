---
title: "виртуальный (C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- virtual_cpp
- virtual
dev_langs:
- C++
helpviewer_keywords:
- virtual base classes [C++], declaring
- base classes [C++], virtual
- virtual functions [C++], declaring
- virtual keyword [C++]
ms.assetid: c2eb987d-6cf3-43b6-aa0c-29a6f561b1ae
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 041939197f18861d27d1f99708e27415de2b7787
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="virtual-c"></a>virtual (C++)
Ключевое слово `virtual` объявляет виртуальную функцию или виртуальный базовый класс.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
virtual [type-specifiers] member-function-declarator  
virtual [access-specifier] base-class-name  
```  
  
#### <a name="parameters"></a>Параметры  
 `type-specifiers`  
 Указывает тип возвращаемого значения виртуальной функции-члена.  
  
 `member-function-declarator`  
 Объявляет функцию-член.  
  
 `access-specifier`  
 Определяет уровень доступа к базовому классу: `public` (открытый), `protected` (защищенный) или `private` (закрытый). Может находиться перед ключевым словом `virtual` или после него.  
  
 `base-class-name`  
 Определяет ранее объявленный тип класса.  
  
## <a name="remarks"></a>Примечания  
 В разделе [виртуальные функции](../cpp/virtual-functions.md) для получения дополнительной информации.  
  
 См. также следующие ключевые слова: [класса](../cpp/class-cpp.md), [закрытый](../cpp/private-cpp.md), [открытый](../cpp/public-cpp.md), и [защищенных](../cpp/protected-cpp.md).  
  
## <a name="see-also"></a>См. также  
 [Ключевые слова](../cpp/keywords-cpp.md)