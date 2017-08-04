---
title: "Целочисленные типы с размером в C | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- sized integer types
ms.assetid: 0d6199b4-d0ab-4e8c-a769-785f5afb92eb
caps.latest.revision: 8
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
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: db04c6862be26d5641a485c47ac7fd71b43d16fe
ms.contentlocale: ru-ru
ms.lasthandoff: 05/18/2017

---
# <a name="c-sized-integer-types"></a>Целочисленные типы размеров C
**Блок, относящийся только к системам Майкрософт**  
  
 В Microsoft C поддерживаются целочисленные типы с указанием размера. Это позволяет объявлять 8-, 16-, 32- и 64-разрядные целочисленные переменные при помощи описателя типа __int*n* (где *n* означает размер целочисленной переменной в битах). Таким образом, *n* может иметь значение 8, 16, 32 или 64. В следующем примере объявляется по одной переменной каждого из 4 целочисленных типов с указанием размера:  
  
```  
__int8 nSmall;      // Declares 8-bit integer  
__int16 nMedium;    // Declares 16-bit integer  
__int32 nLarge;     // Declares 32-bit integer  
__int64 nHuge;      // Declares 64-bit integer  
```  
  
 Первые три целочисленных типа с указанием размера аналогичны типам данных ANSI с таким же размером. Они могут использоваться для написания переносимого кода, который одинаково работает на разных платформах. Обратите внимание, что тип данных __int8 синонимичен типу char, тип \__int16 — типу short, а тип \__int32 — типу int. Тип \__int64 не имеет эквивалента в ANSI.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Хранение базовых типов](../c-language/storage-of-basic-types.md)
