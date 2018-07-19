---
title: виртуальный (C++) | Документация Майкрософт
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
ms.openlocfilehash: 9eba5462caf739d78236e10df018fc07421ea876
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2018
ms.locfileid: "37939124"
---
# <a name="virtual-c"></a>virtual (C++)
**Виртуального** ключевое слово объявляет виртуальную функцию или виртуальный базовый класс.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
virtual [type-specifiers] member-function-declarator  
virtual [access-specifier] base-class-name  
```  
  
#### <a name="parameters"></a>Параметры  
 *Спецификаторы типов*  
 Указывает тип возвращаемого значения виртуальной функции-члена.  
  
 *объявление члена функция*  
 Объявляет функцию-член.  
  
 *спецификатор доступа*  
 Определяет уровень доступа для базового класса, **открытый**, **защищенные** или **частного**. Может отображаться до или после **виртуального** ключевое слово.  
  
 *Base имя класса*  
 Определяет ранее объявленный тип класса.  
  
## <a name="remarks"></a>Примечания  
 См. в разделе [виртуальные функции](../cpp/virtual-functions.md) Дополнительные сведения.  
  
 Также см. следующие ключевые слова: [класс](../cpp/class-cpp.md), [частного](../cpp/private-cpp.md), [открытый](../cpp/public-cpp.md), и [защищенные](../cpp/protected-cpp.md).  
  
## <a name="see-also"></a>См. также  
 [Ключевые слова](../cpp/keywords-cpp.md)