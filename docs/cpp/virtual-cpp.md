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
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 851f911dd7c49df1d685afe63ef5134cf0d5f175
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

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
