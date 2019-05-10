---
title: Ошибка компилятора C2429
ms.date: 11/16/2017
f1_keywords:
- C2429
helpviewer_keywords:
- C2429
ms.assetid: 57ff6df9-5cf1-49f3-8bd8-4e550dfd65a0
ms.openlocfilehash: a5d1e98e91c541729a93f731eede9b047589c63a
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2019
ms.locfileid: "65447982"
---
# <a name="compiler-error-c2429"></a>Ошибка компилятора C2429

> "*языковое средство*«нужен флаг компилятора»*параметр компилятора*"

Возможность языка требует параметр конкретного компилятора для поддержки.

Ошибка **C2429: функцию языка «вложенными, namespace-definition» нужен флаг компилятора "/ std: c ++ 17"** создается при попытке определить *составное пространство имен*, пространство имен, содержащее один или несколько вложенные области имен пространств имен, начиная с обновления 5 Visual Studio 2015. (В Visual Studio 2017 версии 15.3, **/std: c ++ последнюю** коммутатор является обязательным.) Комплексная пространство имен определения не допускаются в C++ до C ++ 17. Компилятор поддерживает определения комплексной пространств имен при [/std: c ++ 17](../../build/reference/std-specify-language-standard-version.md) указан параметр компилятора:

```cpp
// C2429a.cpp
namespace a::b { int i; } // C2429 starting in Visual Studio 2015 Update 3.
                          // Use /std:c++17 to fix, or do this:
// namespace a { namespace b { int i; }}

int main() {
   a::b::i = 2;
}
```
