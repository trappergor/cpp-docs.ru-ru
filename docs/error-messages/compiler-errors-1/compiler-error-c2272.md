---
title: Ошибка компилятора C2272 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2272
dev_langs:
- C++
helpviewer_keywords:
- C2272
ms.assetid: 1517706a-9c27-452e-9b10-3424b3d232bc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e17765ee0acbf20d76e631bf7fccfb3413c5dc1d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46040314"
---
# <a name="compiler-error-c2272"></a>Ошибка компилятора C2272

«функция»: модификаторы недопустимы для статических функций-членов

Объект `static` функция-член объявлен с описателем модели памяти, таких как [const](../../cpp/const-cpp.md) или [volatile](../../cpp/volatile-cpp.md), и такие модификаторы недопустимы для `static` функций-членов.

Следующий пример приводит к возникновению ошибки C2272:

```
// C2272.cpp
// compile with: /c
class CMyClass {
public:
   static void func1() const volatile;   // C2272  func1 is static
   void func2() const volatile;   // OK
};
```