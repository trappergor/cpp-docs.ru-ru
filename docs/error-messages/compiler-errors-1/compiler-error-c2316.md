---
title: Ошибка компилятора C2316 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2316
dev_langs:
- C++
helpviewer_keywords:
- C2316
ms.assetid: 9ad08eb5-060b-4eb0-8d66-0dc134f7bf67
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2868d3a81fcbc94d8b20adcdc775363eb0a8eaeb
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46033021"
---
# <a name="compiler-error-c2316"></a>Ошибка компилятора C2316

> "*исключение*": нельзя перехватить, поскольку деструктор или конструктор копии недоступны

Исключение было перехвачено значением или ссылкой, но конструктор копии и оператор назначения были недоступны.

Этот код был принят в версиях Visual C++ до Visual Studio 2003, но теперь выдает ошибку.

Изменения соответствия в Visual Studio 2015 внесенные этой ошибки, которые применимы к инструкциям неправильный catch исключений MFC, производный от `CException`. Так как `CException` имеет унаследованные закрытый конструктор копии, класс и его производные некопируемых и не может передаваться по значению, а значит и не может быть перехвачены по значению. Перехваченные исключения MFC по значению, ранее привел к неперехваченных исключений во время выполнения операторов catch, но теперь компилятор правильно определяет этой проблеме и отчеты ошибку C2316. Чтобы устранить эту проблему, мы рекомендуем использовать макросы MFC TRY/CATCH, а не создавать собственные обработчики исключений, но если это не подходит для вашего кода, перехватывать исключения MFC по ссылке вместо этого.

## <a name="example"></a>Пример

При компиляции следующего примера возникнет ошибка C2316:

```
// C2316.cpp
// compile with: /EHsc
#include <stdio.h>

extern "C" int printf_s(const char*, ...);

struct B
{
public:
    B() {}
    // Delete the following line to resolve.
private:
    // copy constructor
    B(const B&)
    {
    }
};

void f(const B&)
{
}

int main()
{
    try
    {
        B aB;
        f(aB);
    }
    catch (B b) {   // C2316
        printf_s("Caught an exception!\n");
    }
}
```