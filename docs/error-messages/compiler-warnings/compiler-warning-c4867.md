---
title: Предупреждение компилятора C4867
ms.date: 11/04/2016
f1_keywords:
- C4867
helpviewer_keywords:
- C4867
ms.assetid: 8a257d70-c3a7-462d-b285-e57c952a8bf7
ms.openlocfilehash: 0fd5de46f713aed08508f8755c9e54c3ff46366b
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2019
ms.locfileid: "65447203"
---
# <a name="compiler-warning-c4867"></a>Предупреждение компилятора C4867

«функция»: вызов функции отсутствует список аргументов; Используйте «вызов» для создания указателя на член

Указатель на функцию-член был инициализирован неправильно.

Это предупреждение может возникать в результате действий по обеспечению совместимости компилятора с Visual Studio 2005: расширенным соответствием указателя на член.  Код, скомпилированный в версии до Visual Studio 2005 теперь создаст C4867.

Это предупреждение всегда выдается как ошибка. Используйте прагму [warning](../../preprocessor/warning.md) , чтобы отключить это предупреждение. Дополнительные сведения о C4867 и MFC/ATL, см. в разделе [также библиотеках](../../atl/reference/compiler-options-macros.md#_atl_enable_ptm_warning).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4867.

```
// C4867.cpp
// compile with: /c
class A {
public:
   void f(int) {}

   typedef void (A::*TAmtd)(int);

   struct B {
      TAmtd p;
   };

   void g() {
      B b = {f};   // C4867
      B b2 = {&A::f};   // OK
   }
};
```