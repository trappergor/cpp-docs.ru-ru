---
title: Предупреждение компилятора C4368
ms.date: 11/04/2016
f1_keywords:
- C4368
helpviewer_keywords:
- C4368
ms.assetid: cb85bcee-fd3d-4aa5-b626-2324f07a4f1b
ms.openlocfilehash: b2af1166738d867c84ff4ebae832f831af7940ff
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50485618"
---
# <a name="compiler-warning-c4368"></a>Предупреждение компилятора C4368

Невозможно определить «член» в качестве члена управляемого «тип»: смешанные типы не поддерживаются.

Член данных в собственном формате нельзя внедрять в тип CLR.

Однако, можно объявить указатель на неуправляемый тип и управления его жизненным циклом в конструктора, деструктора и метода завершения управляемого класса. Дополнительные сведения см. в разделе [деструкторы и методы завершения](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).

Это предупреждение всегда выдается как ошибка. Используйте [предупреждение](../../preprocessor/warning.md) директиву pragma, чтобы отключить C4368.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4368.

```
// C4368.cpp
// compile with: /clr /c
struct N {};
ref struct O {};
ref struct R {
    R() : m_p( new N ) {}
    ~R() { delete m_p; }

   property N prop;   // C4368
   int i[10];   // C4368

   property O ^ prop2;   // OK
   N * m_p;   // OK
};
```