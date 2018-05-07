---
title: C3445 Ошибка компилятора | Документы Microsoft
ms.custom: ''
ms.date: 04/10/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3445
dev_langs:
- C++
helpviewer_keywords:
- C3445
ms.assetid: 0d272bfc-136b-4025-a9ba-5e4eea5f8215
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4c37f04b907183b883772fd144ae0179683f088f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3445"></a>C3445 ошибки компилятора

> Список инициализация копии из "*типа*" нельзя использовать явный конструктор

В соответствии с ISO стандарт C ++ 17 компилятор должен учитывать явный конструктор для разрешения перегрузки в инициализация копии списка, но необходимо создание ошибки, если фактический Выбор этой перегрузки.

Начиная с Visual Studio 2017 г., то компилятор находит ошибки, связанные с создания объекта с помощью списка инициализаторов, которые не были найдены по Visual Studio 2015. Эти ошибки может привести к сбоям или неопределенное поведение во время выполнения.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3445.

```cpp
// C3445.cpp
struct A
{
    explicit A(int) {}
    A(double) {}
};

int main()
{
    A a1 = { 1 };     // error C3445: copy-list-initialization of
                      //     'A' cannot use an explicit constructor
}
```

Чтобы исправить эту ошибку, используйте прямой инициализации.

```cpp
// C3445b.cpp
struct A
{
    explicit A(int) {}
    A(double) {}
};

int main()
{
    A a1{ 1 };
}
```
