---
title: "Предупреждение (уровень 1) C4297 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4297
dev_langs:
- C++
helpviewer_keywords:
- C4297
ms.assetid: ba92fcdc-9f70-4f60-abe6-281f9582ca59
caps.latest.revision: 8
author: corob-msft
ms.author: corob
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: c21453d185fed2c33e7cb054e77e1698fadf491b
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4297"></a>Предупреждение компилятора (уровень 1) C4297
function: ожидается, что функция не будет выдавать исключения, но она это делает  
  
 Объявление функции содержит (возможно неявным) `noexcept` описатель, пустой `throw` описатель исключение или [__declspec(nothrow)](../../cpp/nothrow-cpp.md) атрибута и определение содержит один или несколько [throw](../../cpp/try-throw-and-catch-statements-cpp.md) инструкции. Чтобы устранить ошибку C4297, не пытайтесь вызвать исключения в функциях, которые объявлены как `__declspec(nothrow)`, `noexcept(true)` или `throw()`. Кроме того, можно удалить спецификацию `noexcept`, `throw()` или `__declspec(nothrow)`.  
  
 По умолчанию компилятор создает неявные описатели `noexcept(true)` для определяемых пользователем деструкторов и функций deallocator, а также созданных компилятором специальных функций-членов. Это соответствует стандарту ISO C++&11;. Чтобы предотвратить создание noexcept неявные спецификаторы и вернуть компилятору нестандартное поведение Visual Studio 2013, используйте **/Zc:implicitNoexcept-** параметр компилятора. Дополнительные сведения см. в разделе [/Zc: implicitnoexcept (неявные спецификаторы исключений)](../../build/reference/zc-implicitnoexcept-implicit-exception-specifiers.md).  
  
 Дополнительные сведения о спецификации исключений см. в разделе [спецификации исключений (throw)](../../cpp/exception-specifications-throw-cpp.md). Кроме того, в разделе [/EH (модель обработки исключений)](../../build/reference/eh-exception-handling-model.md) сведения об изменении поведения обработки исключений во время компиляции.  
  
 Это предупреждение также генерируется для функций __declspec ([dllexport](../../cpp/dllexport-dllimport.md)) функции помеченные extern «C», даже если они являются функциями C++.  
  
 Следующий пример приводит к возникновению ошибки C4297.  
  
```  
// C4297.cpp  
// compile with: /W1 /LD  
void __declspec(nothrow) f1()   // declared nothrow  
// try the following line instead  
// void f1()  
{  
   throw 1;   // C4297  
}  
```
