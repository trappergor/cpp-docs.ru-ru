---
title: C2429 Ошибка компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/16/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2429
dev_langs:
- C++
helpviewer_keywords:
- C2429
ms.assetid: 57ff6df9-5cf1-49f3-8bd8-4e550dfd65a0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 032df433b28e83f720fe76952a541b59bda889f5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2429"></a>C2429 ошибки компилятора

> "*функции языка*«требуется флаг компилятора»*параметр компилятора*"

Функции языка необходимо использовать параметр компилятора, определенные для поддержки

Ошибка **C2429: функция языка «nested-namespace-definition» требуется флаг компилятора "/ std:c ++ 17'** генерируется при попытке определить *составное пространство имен*, пространство имен, которое содержит один или несколько вложенные области имен, начиная с Visual Studio 2015 обновления 5. (В Visual Studio 2017 г. версия 15,3, **/std: c ++ последнюю** коммутатора не требуется.) Составные пространства имен определения не допускаются в C++ до C ++ 17. Компилятор поддерживает составное пространство имен определения при [/std: c ++ 17](../../build/reference/std-specify-language-standard-version.md) указан параметр компилятора:

```cpp
// C2429a.cpp
namespace a::b { int i; } // C2429 starting in Visual C++ 2015 Update 3.
                          // Use /std:c++17 to fix, or do this:
// namespace a { namespace b { int i; }}

int main() {
   a::b::i = 2;
}
```
