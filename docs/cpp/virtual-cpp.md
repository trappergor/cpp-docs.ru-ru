---
title: виртуальный (C++) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 909fd3fde92479b2e5407608026cb01ec17fced2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
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