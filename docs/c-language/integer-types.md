---
title: Целочисленные типы | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- integer data type, integer types in C++
- integer constants
- integer types
- integers, types
ms.assetid: c8926a5e-0e98-4e37-9b05-ce97961379bd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: acc3dc7631602e8accd9574bf707798dae5ba0d9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="integer-types"></a>Целочисленные типы
Всем целым константам присваивается тип на основе их значения и способа представления. Для любой целой константы можно принудительно задать тип **long**, добавив букву **l** или **L** в конец константы; для принудительного задания типа `unsigned` добавьте в конец значения букву **u** или **U**. Следует избегать использования буквы **l** в нижнем регистре, так как ее можно перепутать с цифрой 1. Ниже приведены некоторые формы целых констант **long**:  
  
```  
/* Long decimal constants */  
10L  
79L  
  
/* Long octal constants */  
012L  
0115L  
  
/* Long hexadecimal constants */  
0xaL or 0xAL  
0X4fL or 0x4FL  
  
/* Unsigned long decimal constant */  
776745UL  
778866LU  
```  
  
 Тип, присваиваемый константе, зависит от значения, которое она представляет. Значение константы должно находиться в диапазоне представимых значений для ее типа. Тип константы определяет, какие преобразования выполняются при использовании константы в выражении или при добавлении знака "минус" (**-**). В этом списке перечислены правила преобразования целых констант.  
  
-   Для десятичной константы без суффикса используется тип `int`, **long int** или **unsigned long int**. Константе присваивается первый из этих 3 типов, в котором возможно представление значения константы.  
  
-   Восьмеричным или шестнадцатеричным константам без суффиксов присваивается тип `int`, `unsigned int`, **long int** или **unsigned long int** в зависимости от размера константы.  
  
-   Константам с суффиксом **u** или **U** в зависимости от их размера присваивается тип **unsigned int** или **unsigned long int**.  
  
-   Константам с суффиксом **l** или **L** в зависимости от их размера присваивается тип **long int** или **unsigned long int**.  
  
-   Константам с суффиксами **u** или **U** и **l** или **L** присваивается тип **unsigned long int**.  
  
## <a name="see-also"></a>См. также  
 [Целочисленные константы в C](../c-language/c-integer-constants.md)