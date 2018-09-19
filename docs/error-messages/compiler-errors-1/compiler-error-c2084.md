---
title: Ошибка компилятора C2084 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2084
dev_langs:
- C++
helpviewer_keywords:
- C2084
ms.assetid: 990b107f-3721-4851-ae8b-4b69a8c149ed
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 09ce703b6908257e37c2b7ff1b2714f1426f941f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46052118"
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