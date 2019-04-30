---
title: Ошибка компилятора C3445
ms.date: 04/10/2017
f1_keywords:
- C3445
helpviewer_keywords:
- C3445
ms.assetid: 0d272bfc-136b-4025-a9ba-5e4eea5f8215
ms.openlocfilehash: 2eddeb5a56c953ca0864e29187fbe28c53bdee24
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62328657"
---
# <a name="compiler-error-c3445"></a>Ошибка компилятора C3445

> Copy-list-initialization из "*тип*" нельзя использовать явный конструктор

В соответствии с ISO стандарт C ++ 17 компилятор должен учитывать явный конструктор для разрешения перегрузки в copy-list-initialization, но должен выдавать ошибку, если эта перегрузка выбирается на самом деле.

Начиная с Visual Studio 2017, компилятор обнаруживает ошибки, связанные с созданием объектов с помощью списка инициализаторов, которые не были найдены по Visual Studio 2015. Эти ошибки может привести к сбоям или неопределенному поведению во время выполнения.

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

Чтобы исправить эту ошибку, вместо этого используйте прямую инициализацию:

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
