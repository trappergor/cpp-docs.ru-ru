---
title: Ошибка компилятора C2732 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2732
dev_langs:
- C++
helpviewer_keywords:
- C2732
ms.assetid: 01b7ad2c-93cf-456f-a4c0-c5f2fdc7c07c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 040fd73bcb69ef032d5c6150bb157337f34a2088
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46079665"
---
# <a name="compiler-error-c2732"></a>Ошибка компилятора C2732

спецификация компоновки противоречит более ранней спецификации function

Функция уже объявлена с другим описателем компоновки.

Эта ошибка может возникать при включении файлов с различными описателями компоновки.

Для устранения этой ошибки измените оператор `extern`, чтобы согласовать компоновки. В частности, не заключайте директивы `#include` в блоки `extern "C"`.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2732:

```
// C2732.cpp
extern void func( void );   // implicit C++ linkage
extern "C" void func( void );   // C2732
```