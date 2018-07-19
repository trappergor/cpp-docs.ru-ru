---
title: Предупреждение (уровень 3) C4373 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4373
dev_langs:
- C++
helpviewer_keywords:
- C4373
ms.assetid: 670c0ba3-b7d6-4aed-b207-1cb84da3bcde
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fda965fe80fc26731cde7be5a71540e6454a7360
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33290183"
---
# <a name="compiler-warning-level-3-c4373"></a>Предупреждение компилятора (уровень 3) C4373

> "*функция*": переопределение виртуальной функции*базовая_функция*", предыдущие версии компилятора не выполняли переопределение, когда параметры отличались только квалификаторами const или volatile

## <a name="remarks"></a>Примечания

Ваше приложение содержит метод в производном классе, который переопределяет виртуальный метод в базовом классе, и параметры в переопределяющем методе отличаются от параметров виртуального метода только по квалификатору [const](../../cpp/const-cpp.md) или [volatile](../../cpp/volatile-cpp.md) . Это означает, что компилятор должен привязать ссылку на функцию к методу в базовом или производном классе.

Версии компилятора до Visual Studio 2008 привязывают функцию к методу в базовом классе, а затем выдают предупреждение. Игнорировать последующие версии компилятора `const` или `volatile` квалификатор, привязывают функцию к методу в производном классе, а затем выдают предупреждение **C4373**. Поведение в последнем случае соответствует стандарту C++.

## <a name="example"></a>Пример

Следующий пример кода приводит к возникновению ошибки C4373. Чтобы устранить эту проблему, можно сделать переопределение служит же CV-квалификаторы функции-члена базового или если оно не должно предоставляться создайте переопределение, можно присвоить функция в производном классе другое имя.

```cpp
// c4373.cpp
// compile with: /c /W3
#include <stdio.h>
struct Base
{
    virtual void f(int i) {
        printf("base\n");
    }
};

struct Derived : Base
{
    void f(const int i) {  // C4373
        printf("derived\n");
    }
};

void main()
{
    Derived d;
    Base* p = &d;
    p->f(1);
}
```

```Output
derived
```