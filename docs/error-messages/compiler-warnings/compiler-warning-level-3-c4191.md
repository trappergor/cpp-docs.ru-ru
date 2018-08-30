---
title: Предупреждение компилятора (уровень 3) C4191 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4191
dev_langs:
- C++
helpviewer_keywords:
- C4191
ms.assetid: 576d3bc6-95b7-448a-af31-5d798452df09
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c3b0198971064bec114e4665a499e070ddb61501
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43197502"
---
# <a name="compiler-warning-level-3-c4191"></a>Предупреждение компилятора (уровень 3) C4191
"оператор/операция": небезопасное преобразование из типа "тип выражения" в тип "требуемый тип"  
  
 Некоторые операции с участием указателей функций считаются небезопасными.  
  
-   Типы функций с разными соглашениями о вызовах.  
  
-   Типы функций с разными соглашениями о возвратах.  
  
-   Типы аргументов или типы возвратов с разными размерами, типами категорий или классификациями.  
  
-   Списки аргументов разной длины (в `__cdecl`, только при приведении длинного списка к более короткому списку, даже если более короткий список содержит аргументы переменной длины).  
  
-   Указатель на данные (отличные от **void**<strong>\*</strong>), являющийся псевдонимом для указателя на функцию.  
  
-   Любые другие различия между типами, которые дадут ошибку или предупреждение в `reinterpret_cast`.  
  
 Вызов этой функции через результирующий указатель может вызвать сбой программы.  
  
 Это предупреждение отключено по умолчанию. Подробнее: [Выключенные по умолчанию предупреждения компилятора](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .  
  
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