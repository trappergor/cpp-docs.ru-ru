---
title: void (C++) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- void_cpp
dev_langs:
- C++
helpviewer_keywords:
- void keyword [C++]
- functions [C++], void
- pointers, void
ms.assetid: d203edba-38e6-4056-8b89-011437351057
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: de70ec6758109bc765d0cec3552762288d51ded2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="void-c"></a>void (C++)
Если ключевое слово `void` указывает возвращаемый тип функции, оно означает, что данная функция не возвращает никакого значения. Если оно используется для списка параметров функции, оно означает, что функция не принимает никаких параметров. Если оно используется в объявлении указателя, оно означает, что указатель является "универсальным".  
  
 Если указатель имеет тип **void \***, указатель может указывать на любой переменной, которая не объявлен со **const** или `volatile` ключевое слово. Указатель с ключевым словом void не может быть разыменован, кроме как путем приведения к другому типу. Указатель с ключевым словом void может быть преобразован в любой другой тип указателя на данные.  
  
 В C++ указатель с ключевым словом void может указывать на функцию, но не на класса.  
  
 Объявить переменную типа void невозможно.  
  
## <a name="example"></a>Пример  
  
```  
// void.cpp  
void vobject;   // C2182  
void *pv;   // okay  
int *pint; int i;  
int main() {  
   pv = &i;  
   // Cast optional in C required in C++  
   pint = (int *)pv;  
}   
```  
  
## <a name="see-also"></a>См. также  
 [Ключевые слова](../cpp/keywords-cpp.md)   
 [Фундаментальные типы](../cpp/fundamental-types-cpp.md)