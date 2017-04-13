---
title: "Предупреждение (уровень 3) C4191 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4191
dev_langs:
- C++
helpviewer_keywords:
- C4191
ms.assetid: 576d3bc6-95b7-448a-af31-5d798452df09
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 5cdd66e6318867a7f4df8ff70b6440ae6e7bfa3a
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-3-c4191"></a>Предупреждение компилятора (уровень 3) C4191
"оператор/операция": небезопасное преобразование из типа "тип выражения" в тип "требуемый тип"  
  
 Некоторые операции с участием указателей функций считаются небезопасными.  
  
-   Типы функций с разными соглашениями о вызовах.  
  
-   Типы функций с разными соглашениями о возвратах.  
  
-   Типы аргументов или типы возвратов с разными размерами, типами категорий или классификациями.  
  
-   Списки аргументов разной длины (в `__cdecl`, только при приведении длинного списка к более короткому списку, даже если более короткий список содержит аргументы переменной длины).  
  
-   Указатель на данные (кроме **void\***), являющийся псевдонимом для указателя на функцию.  
  
-   Любые другие различия между типами, которые дадут ошибку или предупреждение в `reinterpret_cast`.  
  
 Вызов этой функции через результирующий указатель может вызвать сбой программы.  
  
 Это предупреждение отключено по умолчанию. В разделе [компилятора предупреждения выключенные по умолчанию](../../preprocessor/compiler-warnings-that-are-off-by-default.md) для получения дополнительной информации.  
  
 Следующий пример приводит к возникновению ошибки C4191:  
  
```  
// C4191.cpp  
// compile with: /W3 /clr  
#pragma warning(default: 4191)  
  
void __clrcall f1() { }  
void __cdecl   f2() { }  
  
typedef void (__clrcall * fnptr1)();  
typedef void (__cdecl   * fnptr2)();  
  
int main() {  
   fnptr1 fp1 = static_cast<fnptr1>(&f1);  
   fnptr2 fp2 = (fnptr2) &f2;  
  
   fnptr1 fp3 = (fnptr1) &f2;   // C4191  
   fnptr2 fp4 = (fnptr2) &f1;   // C4191  
};  
```
