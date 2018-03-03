---
title: "C2429 Ошибка компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/16/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2429
dev_langs:
- C++
helpviewer_keywords:
- C2429
ms.assetid: 57ff6df9-5cf1-49f3-8bd8-4e550dfd65a0
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6882804d1ddf2e4f83947e310cde4c8c114120d1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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
