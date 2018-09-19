---
title: Предупреждение компилятора C4867 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4867
dev_langs:
- C++
helpviewer_keywords:
- C4867
ms.assetid: 8a257d70-c3a7-462d-b285-e57c952a8bf7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b444156ae87e43b068521a3ad6687abe71df293f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46074322"
---
# <a name="compiler-warning-c4867"></a>Предупреждение компилятора C4867

«функция»: вызов функции отсутствует список аргументов; Используйте «вызов» для создания указателя на член

Указатель на функцию-член был инициализирован неправильно.

Это предупреждение может возникать в результате действий по обеспечению совместимости компилятора с Visual C++ 2005: расширенным соответствием указателя на член.  Код, скомпилированный в версии до Visual C++ 2005 теперь создаст C4867.

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