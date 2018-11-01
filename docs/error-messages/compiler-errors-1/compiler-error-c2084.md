---
title: Ошибка компилятора C2084
ms.date: 11/04/2016
f1_keywords:
- C2084
helpviewer_keywords:
- C2084
ms.assetid: 990b107f-3721-4851-ae8b-4b69a8c149ed
ms.openlocfilehash: 9aaf3a88e63234dfb842e4b48afd6e55595e96ca
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50571318"
---
# <a name="compiler-error-c2084"></a>Ошибка компилятора C2084

функция "*функция*" уже имеет текст реализации

Функция уже определена.

В версиях Visual C++ до Visual Studio 2002 г.,

- Компилятор будет принимать несколько специализаций шаблонов, которые разрешаются в том же фактический тип, несмотря на то, что никогда не будут доступны дополнительные определения. Компилятор теперь обнаруживает эти несколько определений.

- `__int32` и `int` отсутствуют, рассматриваются как отдельные типы. Теперь компилятор считает `__int32` как синоним для `int`. Это означает, что компилятор обнаружил несколько определений, если функция перегружена на обоих `__int32` и `int` и выдает ошибку.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2084:

```cpp
// C2084.cpp
void Func(int);
void Func(int) {}   // define function
void Func(int) {}   // C2084 second definition
```

Чтобы исправить эту ошибку, удалите повторяющееся определение:

```
// C2084b.cpp
// compile with: /c
void Func(int);
void Func(int) {}
```