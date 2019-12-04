---
title: Ошибка компилятора C3063
ms.date: 11/04/2016
f1_keywords:
- C3063
helpviewer_keywords:
- C3063
ms.assetid: 0ecf6f1f-e4a7-487a-9fd5-79d8ac470001
ms.openlocfilehash: c52a0a4c4255eeed5f49a7e6c1e86a1f64b8ad77
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755659"
---
# <a name="compiler-error-c3063"></a>Ошибка компилятора C3063

оператор "operator": все операнды должны иметь одинаковый тип перечисления

При использовании операторов в перечислителях оба операнда должны иметь тип перечисления. Дополнительные сведения см. [в разделе инструкции. Определение и использование перечислений C++в/CLI](../../dotnet/how-to-define-and-consume-enums-in-cpp-cli.md).

## <a name="example"></a>Пример

В следующем примере создается C3063 и демонстрируется его устранение.

```cpp
// C3063.cpp
// compile with: /clr
enum class E { a, b } e, mask;
int main() {
   if ( ( e & mask ) != 0 ) ;   // C3063 no operator!= (E, int)

   if ( ( e & mask ) != E() )   // OK
      ;
}
```
