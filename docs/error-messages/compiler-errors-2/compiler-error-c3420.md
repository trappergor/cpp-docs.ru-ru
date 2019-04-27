---
title: Ошибка компилятора C3420
ms.date: 11/04/2016
f1_keywords:
- C3420
helpviewer_keywords:
- C3420
ms.assetid: 99b53c77-f36b-4574-9199-b53111becccb
ms.openlocfilehash: 3db109598ce0741ca34a230d8925994543bcb5ea
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62182461"
---
# <a name="compiler-error-c3420"></a>Ошибка компилятора C3420

"метод_завершения": метод завершения не может быть виртуальным

Метод завершения можно вызвать только не виртуально из его включающего типа. Следовательно, это ошибка для объявления виртуального метода завершения.

Дополнительные сведения см. в разделе [деструкторы и методы завершения в разделе: Определение и использование классов и структур (C++выполняет)](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).

## <a name="example"></a>Пример

При компиляции следующего примера возникнет ошибка C3420.

```
// C3420.cpp
// compile with: /clr /c
ref class R {
   virtual !R() {}   // C3420
};
```