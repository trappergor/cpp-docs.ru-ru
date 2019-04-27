---
title: Ошибка компилятора C2959
ms.date: 11/04/2016
f1_keywords:
- C2959
helpviewer_keywords:
- C2959
ms.assetid: d66bb2a8-70c3-4209-a358-b0c47f111a50
ms.openlocfilehash: 3465c3275783a625c172b711e9c41789b6f36713
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62256884"
---
# <a name="compiler-error-c2959"></a>Ошибка компилятора C2959

Универсальный класс или функция не может быть членом шаблона

Дополнительные сведения см. в разделе [среды выполнения Windows и управляемые шаблоны](../../extensions/windows-runtime-and-managed-templates-cpp-component-extensions.md) и [универсальные шаблоны](../../extensions/generics-cpp-component-extensions.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2959.

```
// C2959.cpp
// compile with: /clr /c
template <class T> ref struct S {
   generic <class U> ref struct GR1;   // C2959
};
```