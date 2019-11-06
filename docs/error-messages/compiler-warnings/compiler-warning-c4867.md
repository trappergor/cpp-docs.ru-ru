---
title: Предупреждение компилятора C4867
ms.date: 11/04/2016
f1_keywords:
- C4867
helpviewer_keywords:
- C4867
ms.assetid: 8a257d70-c3a7-462d-b285-e57c952a8bf7
ms.openlocfilehash: e093d262bc26cf0acfbb181d621fffc1aa391ee9
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/05/2019
ms.locfileid: "73626591"
---
# <a name="compiler-warning-c4867"></a>Предупреждение компилятора C4867

"функция": в вызове функции отсутствует список аргументов; Используйте "Call" для создания указателя на член

Неверно инициализирован указатель на функцию-член.

Это предупреждение можно создать в результате работы по согласованности компилятора, выполненной для Visual Studio 2005: расширенное соответствие указателю на элемент.  Код, скомпилированный до Visual Studio 2005, теперь создаст C4867.

Это предупреждение всегда выдается как ошибка. Используйте прагму [warning](../../preprocessor/warning.md) , чтобы отключить это предупреждение. Дополнительные сведения о C4867 и MFC/ATL см. в разделе [_ATL_ENABLE_PTM_WARNING](../../atl/reference/compiler-options-macros.md#_atl_enable_ptm_warning).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4867.

```cpp
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