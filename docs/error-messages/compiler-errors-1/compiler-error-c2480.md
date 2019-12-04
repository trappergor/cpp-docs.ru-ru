---
title: Ошибка компилятора C2480
ms.date: 11/04/2016
f1_keywords:
- C2480
helpviewer_keywords:
- C2480
ms.assetid: 1a58d1c2-971b-4084-96fa-f94aa51c02f1
ms.openlocfilehash: 3e495a8019405a558511637467133877dae1183e
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74743527"
---
# <a name="compiler-error-c2480"></a>Ошибка компилятора C2480

"идентификатор": "Thread" допустим только для элементов данных в статическом экстенте

Атрибут `thread` нельзя использовать с автоматической переменной, нестатическим элементом данных, параметром функции или объявлениями или определениями функций.

Используйте атрибут `thread` для глобальных переменных, статических элементов данных и локальных статических переменных.

Следующий пример приводит к возникновению ошибки C2480:

```cpp
// C2480.cpp
// compile with: /c
__declspec( thread ) void func();   // C2480
__declspec( thread ) static int i;   // OK
```
