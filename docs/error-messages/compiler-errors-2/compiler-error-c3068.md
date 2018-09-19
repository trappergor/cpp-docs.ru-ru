---
title: Ошибка компилятора C3068 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3068
dev_langs:
- C++
helpviewer_keywords:
- C3068
ms.assetid: 613e3447-b4a8-4268-a661-297bed63ccdf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fdea26e204032c27f00639ee46a928c7bf084a4e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46035628"
---
# <a name="compiler-error-c3068"></a>Ошибка компилятора C3068

«функция»: функцию «голым» не может содержать объекты, требующие развертывания обработки при возникновении исключения C++

Компилятору не удалось выполнить развертывание стека на [с атрибутом naked](../../cpp/naked-cpp.md) функцию, которая создала исключение, так как временный объект был создан в функции и обработки исключений C++ ([/EHsc](../../build/reference/eh-exception-handling-model.md)) был указан.

Чтобы устранить эту ошибку, выполните по крайней мере одно из следующих действий.

- Не компилировать с/EHsc.

- Не следует помечать функцию как `naked`.

- Не создавайте временного объекта в функции.

Если функция создает временный объект в стеке, функция создает исключение, если включена обработка исключений C++, компилятор очистит вверх по стеку, если возникает исключение.

Когда возникает исключение, созданный компилятором код пролог и эпилог, а какие не существуют в функции с атрибутом naked, выполняется для функции.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3068:

```
// C3068.cpp
// compile with: /EHsc
// processor: x86
class A {
public:
   A(){}
   ~A(){}
};

void b(A){}

__declspec(naked) void c() {
   b(A());   // C3068
};
```