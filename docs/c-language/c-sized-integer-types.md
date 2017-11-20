---
title: "Целочисленные типы с размером в C | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: sized integer types
ms.assetid: 0d6199b4-d0ab-4e8c-a769-785f5afb92eb
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 101c8facb8871d814d1a1ea05c2856d3105a8bfc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
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