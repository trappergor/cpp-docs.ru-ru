---
title: void (C++) | Документация Майкрософт
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
ms.openlocfilehash: dbb46302c2ae8834ab9a2a626a3bfb77c41996a2
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/02/2018
ms.locfileid: "39461482"
---
# <a name="void-c"></a>void (C++)
При использовании в качестве возвращаемого типа функции, **void** ключевое слово указывает, что функция не возвращает значение. Если оно используется для списка параметров функции, оно означает, что функция не принимает никаких параметров. Если оно используется в объявлении указателя, оно означает, что указатель является "универсальным".  
  
 Если указатель имеет тип `void *`, он может указывать на любую переменную, объявленную без **const** или **volatile** ключевое слово. Указатель с ключевым словом void не может быть разыменован, кроме как путем приведения к другому типу. Указатель с ключевым словом void может быть преобразован в любой другой тип указателя на данные.  
  
 В C++ указатель с ключевым словом void может указывать на функцию, но не на класса.  
  
 Объявить переменную типа void невозможно.  
  
## <a name="example"></a>Пример  
  
```cpp 
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