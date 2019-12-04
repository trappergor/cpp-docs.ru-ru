---
title: Ошибка компилятора C2208
ms.date: 11/04/2016
f1_keywords:
- C2208
helpviewer_keywords:
- C2208
ms.assetid: 9ae704bc-bf70-45f1-8e47-0470f21edd4e
ms.openlocfilehash: 208e15e98a05089c0e9b1c98400f5267e4f3a48f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758935"
---
# <a name="compiler-error-c2208"></a>Ошибка компилятора C2208

"тип": ни один член не определен с помощью этого типа

Идентификатор, который разрешается в имя типа, находится в обобщенном объявлении, но компилятор не может объявить член.

Следующий пример приводит к возникновению ошибки C2208:

```cpp
// C2208.cpp
class C {
   C;   // C2208
   C(){}   // OK
};
```
