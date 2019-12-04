---
title: Ошибка компилятора C2474
ms.date: 11/04/2016
f1_keywords:
- C2474
helpviewer_keywords:
- C2474
ms.assetid: 64e6c61e-6e77-480e-bcf0-b30a2fc482ac
ms.openlocfilehash: ed2ba0d80ffcf2ef83abd551026bc6df4939ffbd
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74743735"
---
# <a name="compiler-error-c2474"></a>Ошибка компилятора C2474

"ключевое_слово": отсутствует соседняя точка с запятой; может представлять ключевое слово или идентификатор

Компилятор ожидал встретить точку с запятой, ему не удалось определить ваше намерение. Добавьте точку с запятой, чтобы устранить эту ошибку.

## <a name="example"></a>Пример

При компиляции следующего примера возникнет ошибка C2474:

```cpp
// C2474.cpp
// compile with: /clr /c

ref class A {
   ref class B {}
   property int i;   // C2474 error
};

// OK
ref class B {
   ref class D {};
   property int i;
};

ref class E {
   ref class F {} property;
   int i;
};
```
