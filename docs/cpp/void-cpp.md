---
title: "void (C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a800aca290a178e3b193c245df515385311b5593
ms.sourcegitcommit: 9239c52c05e5cd19b6a72005372179587a47a8e4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2018
---
# <a name="void-c"></a>void (C++)
Если ключевое слово `void` указывает возвращаемый тип функции, оно означает, что данная функция не возвращает никакого значения. Если оно используется для списка параметров функции, оно означает, что функция не принимает никаких параметров. Если оно используется в объявлении указателя, оно означает, что указатель является "универсальным".  
  
 Если указатель имеет тип **void \*** , указатель может указывать на любой переменной, которая не объявлен со **const** или `volatile` ключевое слово. Указатель с ключевым словом void не может быть разыменован, кроме как путем приведения к другому типу. Указатель с ключевым словом void может быть преобразован в любой другой тип указателя на данные.  
  
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