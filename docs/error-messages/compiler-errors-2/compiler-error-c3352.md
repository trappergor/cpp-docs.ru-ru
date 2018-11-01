---
title: Ошибка компилятора C3352
ms.date: 11/04/2016
f1_keywords:
- C3352
helpviewer_keywords:
- C3352
ms.assetid: f233bed7-474e-425f-aad2-7801578169d4
ms.openlocfilehash: c45ce5e2e72c6a987a0053cb4b1bbb151c149faf
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50496546"
---
# <a name="compiler-error-c3352"></a>Ошибка компилятора C3352

«функция»: указанная функция не соответствует типу делегата «тип»

Их списки параметров для `function` и делегат не совпадают.

Дополнительные сведения см. в разделе [delegate (расширения компонентов C++)](../../windows/delegate-cpp-component-extensions.md).

Следующий пример приводит к возникновению ошибки C3352:

```
// C3352.cpp
// compile with: /clr
delegate int D( int, int );
ref class C {
public:
   int mf( int ) {
      return 1;
   }

   // Uncomment the following line to resolve.
   // int mf(int, int) { return 1; }
};

int main() {
   C^ pC = gcnew C;
   System::Delegate^ pD = gcnew D( pC, &C::mf );   // C3352
}
```
