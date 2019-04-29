---
title: Ошибка компилятора C3807
ms.date: 11/04/2016
f1_keywords:
- C3807
helpviewer_keywords:
- C3807
ms.assetid: 7e2b0aab-8c61-4e71-b9c1-fcaeb6a1b5ea
ms.openlocfilehash: b5599914666af95a29667acc1ad4ad35eef7608f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391937"
---
# <a name="compiler-error-c3807"></a>Ошибка компилятора C3807

«Тип»: класс с атрибутом ComImport не может наследовать от «тип2», то разрешено только реализация интерфейса

Тип, производный от <xref:System.Runtime.InteropServices.ComImportAttribute> только можно реализовать интерфейс.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3807.

```
// C3807.cpp
// compile with: /clr /c
ref struct S {};
interface struct I {};

[System::Runtime::InteropServices::ComImportAttribute()]
ref struct S1 : S {};   // C3807
ref struct S2 : I {};
```