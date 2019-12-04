---
title: Ошибка компилятора C2894
ms.date: 11/04/2016
f1_keywords:
- C2894
helpviewer_keywords:
- C2894
ms.assetid: 4e250579-2b59-4993-a6f4-49273e7ecf06
ms.openlocfilehash: ffc87008c1874f8f5c7e275778237f611dcbb5af
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760827"
---
# <a name="compiler-error-c2894"></a>Ошибка компилятора C2894

Невозможно объявить шаблоны, чтобы они имели компоновку "C"

Эта ошибка может быть вызвана шаблоном, определенным в блоке `extern` "C".

Следующий пример приводит к возникновению ошибки C2894:

```cpp
// C2894.cpp
extern "C" {
   template<class T> class stack {};   // C2894 fail

   template<class T> void f(const T &aT) {}   // C2894
}
```

Следующий пример приводит к возникновению ошибки C2894:

```cpp
// C2894b.cpp
// compile with: /c
extern "C" template<class T> void f(const T &aT) {}   // C2894

template<class T> void f2(const T &aT) {}   // OK
```
