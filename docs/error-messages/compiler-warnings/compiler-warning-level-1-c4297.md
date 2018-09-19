---
title: Предупреждение компилятора (уровень 1) C4297 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4297
dev_langs:
- C++
helpviewer_keywords:
- C4297
ms.assetid: ba92fcdc-9f70-4f60-abe6-281f9582ca59
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f615df5933cfc93918b05758f042c8cf47aa92f1
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46099438"
---
# <a name="compiler-warning-level-1-c4297"></a>Предупреждение компилятора (уровень 1) C4297

function: ожидается, что функция не будет выдавать исключения, но она это делает

Объявление функции содержит (возможно, неявно) `noexcept` описатель, пустой `throw` описатель исключения или [__declspec(nothrow)](../../cpp/nothrow-cpp.md) атрибута и определение содержит один или несколько [throw ](../../cpp/try-throw-and-catch-statements-cpp.md) инструкций. Чтобы устранить ошибку C4297, не пытайтесь вызвать исключения в функциях, которые объявлены как `__declspec(nothrow)`, `noexcept(true)` или `throw()`. Кроме того, можно удалить спецификацию `noexcept`, `throw()` или `__declspec(nothrow)`.

По умолчанию компилятор создает неявные описатели `noexcept(true)` для определяемых пользователем деструкторов и функций deallocator, а также созданных компилятором специальных функций-членов. Это соответствует стандарту ISO C++ 11. Для предотвращения создания спецификаторов неявных описателей noexcept и вернуть компилятору нестандартное поведение Visual Studio 2013, используйте **/Zc:implicitNoexcept-** параметр компилятора. Дополнительные сведения см. в разделе [/Zc: implicitnoexcept (неявные описатели исключений)](../../build/reference/zc-implicitnoexcept-implicit-exception-specifiers.md).

Дополнительные сведения о спецификациях исключений см. в разделе [спецификации исключений (throw)](../../cpp/exception-specifications-throw-cpp.md). Кроме того, см. в разделе [/EH (модель обработки исключений)](../../build/reference/eh-exception-handling-model.md) сведения об изменении поведения обработки исключений во время компиляции.

Это предупреждение также выдается для __declspec ([dllexport](../../cpp/dllexport-dllimport.md)) функции обозначены extern «C», даже если они являются функциями C++.

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