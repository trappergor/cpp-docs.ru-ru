---
title: Ошибка компилятора C3292
ms.date: 11/04/2016
f1_keywords:
- C3292
helpviewer_keywords:
- C3292
ms.assetid: ead485cc-5471-4e10-b361-300589ff5b70
ms.openlocfilehash: 7c59932a79534a365a20fcad25583f7addc0d624
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50609613"
---
# <a name="compiler-error-c3292"></a>Ошибка компилятора C3292

пространство имен CLI нельзя открыть повторно

Пространство имен cli не может быть объявлено в вашем коде.  Дополнительные сведения см. в разделе [Platform, default и cli пространства имен](../../windows/platform-default-and-cli-namespaces-cpp-component-extensions.md).

## <a name="example"></a>Пример

В следующем примере возникает ошибка C3292.

```
// C3292.cpp
// compile with: /clr /c
namespace cli {};   // C3292
```