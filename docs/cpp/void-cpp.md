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
ms.openlocfilehash: 81dd7717940bb6f78063b0fba64dd5d7f8cad583
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2018
ms.locfileid: "37944507"
---
# <a name="void-c"></a>void (C++)
При использовании в качестве возвращаемого типа функции, **void** ключевое слово указывает, что функция не возвращает значение. Если оно используется для списка параметров функции, оно означает, что функция не принимает никаких параметров. Если оно используется в объявлении указателя, оно означает, что указатель является "универсальным".  
  
 Если указатель имеет тип **void \*** , он может указывать на любую переменную, объявленную без **const** или **volatile** ключевое слово. Указатель с ключевым словом void не может быть разыменован, кроме как путем приведения к другому типу. Указатель с ключевым словом void может быть преобразован в любой другой тип указателя на данные.  
  
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