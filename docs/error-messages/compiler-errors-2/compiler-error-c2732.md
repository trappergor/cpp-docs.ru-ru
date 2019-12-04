---
title: Ошибка компилятора C2732
ms.date: 11/04/2016
f1_keywords:
- C2732
helpviewer_keywords:
- C2732
ms.assetid: 01b7ad2c-93cf-456f-a4c0-c5f2fdc7c07c
ms.openlocfilehash: 61bac8c1b5c9e029cc5833f458669b490fed8c91
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755802"
---
# <a name="compiler-error-c2732"></a>Ошибка компилятора C2732

спецификация компоновки противоречит более ранней спецификации function

Функция уже объявлена с другим описателем компоновки.

Эта ошибка может возникать при включении файлов с различными описателями компоновки.

Для устранения этой ошибки измените оператор `extern`, чтобы согласовать компоновки. В частности, не заключайте директивы `#include` в блоки `extern "C"`.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2732:

```cpp
// C2732.cpp
extern void func( void );   // implicit C++ linkage
extern "C" void func( void );   // C2732
```
