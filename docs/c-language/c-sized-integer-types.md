---
title: Целочисленные типы с размером в C | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- sized integer types
ms.assetid: 0d6199b4-d0ab-4e8c-a769-785f5afb92eb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4a61d9ae386efb25171cfdbedc5889c1ffa76e30
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32381867"
---
# <a name="c-sized-integer-types"></a>Целочисленные типы размеров C
**Блок, относящийся только к системам Microsoft**  
  
 В Microsoft C поддерживаются целочисленные типы с указанием размера. Это позволяет объявлять 8-, 16-, 32- и 64-разрядные целочисленные переменные при помощи спецификатора типа __int*n* (где *n* означает размер целочисленной переменной в битах). Таким образом, *n* может иметь значение 8, 16, 32 или 64. В следующем примере объявляется по одной переменной каждого из 4 целочисленных типов с указанием размера:  
  
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