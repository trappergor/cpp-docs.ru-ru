---
title: Предупреждение компилятора C4368 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4368
dev_langs:
- C++
helpviewer_keywords:
- C4368
ms.assetid: cb85bcee-fd3d-4aa5-b626-2324f07a4f1b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 52026f08a56faa1372b73b94fe91c96682510038
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46073217"
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