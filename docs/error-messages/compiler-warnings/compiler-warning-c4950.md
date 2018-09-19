---
title: Предупреждение компилятора C4950 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4950
dev_langs:
- C++
helpviewer_keywords:
- C4950
ms.assetid: 50226a5c-c664-4d09-ac59-e9e874ca244f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 750295da5d2da42ae4c2aac4fbb04dd208a7f32c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46072216"
---
# <a name="compiler-warning-c4950"></a>Предупреждение компилятора C4950

"тип_или_член": помечен как устаревший

Член или тип был помечен как устаревший с помощью <xref:System.ObsoleteAttribute> атрибута.

C4950 всегда выдается как ошибка. Это предупреждение можно отключить с помощью [предупреждение](../../preprocessor/warning.md) директиву pragma или [/wd](../../build/reference/compiler-option-warning-level.md) параметр компилятора.

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