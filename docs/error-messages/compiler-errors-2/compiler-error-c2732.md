---
title: Ошибка компилятора C2732
ms.date: 11/04/2016
f1_keywords:
- C2732
helpviewer_keywords:
- C2732
ms.assetid: 01b7ad2c-93cf-456f-a4c0-c5f2fdc7c07c
ms.openlocfilehash: 78be424040c7315271d0880c6678584f698b5be8
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218186"
---
# <a name="compiler-error-c2732"></a>Ошибка компилятора C2732

спецификация компоновки противоречит более ранней спецификации function

Функция уже объявлена с другим описателем компоновки.

Эта ошибка может возникать при включении файлов с различными описателями компоновки.

Чтобы устранить эту ошибку, измените **`extern`** инструкции таким образом, чтобы они были согласованы. В частности, не заключайте директивы `#include` в блоки `extern "C"`.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2732:

```cpp
// C2732.cpp
extern void func( void );   // implicit C++ linkage
extern "C" void func( void );   // C2732
```
