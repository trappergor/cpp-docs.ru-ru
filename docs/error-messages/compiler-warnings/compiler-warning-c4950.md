---
title: Предупреждение компилятора C4950
ms.date: 11/04/2016
f1_keywords:
- C4950
helpviewer_keywords:
- C4950
ms.assetid: 50226a5c-c664-4d09-ac59-e9e874ca244f
ms.openlocfilehash: 52c4de94dfe087b4dcf407295e556c9350b2cb8b
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80164993"
---
# <a name="compiler-warning-c4950"></a>Предупреждение компилятора C4950

"тип_или_член": помечен как устаревший

Элемент или тип был помечен атрибутом <xref:System.ObsoleteAttribute> как устаревший.

C4950 всегда выдается как ошибка. Это предупреждение можно отключить с помощью директивы pragma [warning](../../preprocessor/warning.md) или параметра компилятора [/WD](../../build/reference/compiler-option-warning-level.md) .

## <a name="example"></a>Пример

В следующем примере возникает ошибка C4950:

```cpp
// C4950.cpp
// compile with: /clr
using namespace System;

// Any reference to Func3 should generate an error with message
[System::ObsoleteAttribute("Will be removed in next version", true)]
Int32 Func3(Int32 a, Int32 b) {
   return (a + b);
}

int main() {
   Int32 MyInt3 = ::Func3(2, 2);   // C4950
}
```
