---
title: Предупреждение компилятора C4430
ms.date: 11/04/2016
f1_keywords:
- C4430
helpviewer_keywords:
- C4430
ms.assetid: 12efbfff-aa58-4a86-a7d6-2c6a12d01dd3
ms.openlocfilehash: 1d58efd57433a065f08e4111302f358405e3b9ab
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62311440"
---
# <a name="compiler-warning-c4430"></a>Предупреждение компилятора C4430

отсутствует спецификатор типа — предполагается int. Примечание. C++ не поддерживает int по умолчанию

Эта ошибка может возникать в результате действий по обеспечению совместимости компилятора с Visual C++ 2005: все объявления должны явно указывать тип; int больше не предполагается.

C4430 всегда выдается как ошибка.  Вы можете отключить это предупреждение с помощью `#pragma warning` или **/wd**; см. в разделе [предупреждение](../../preprocessor/warning.md) или [/w, / W0, / W1, / w2, / w3, / W4, / W1, / w2, / w3, / W4, / Wall, / WD, / we, / WO, / wv, /WX (уровень предупреждений)](../../build/reference/compiler-option-warning-level.md)Дополнительные сведения.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4430.

```
// C4430.cpp
// compile with: /c
struct CMyClass {
   CUndeclared m_myClass;  // C4430
   int m_myClass;  // OK
};

typedef struct {
   POINT();   // C4430
   // try the following line instead
   // int POINT();
   unsigned x;
   unsigned y;
} POINT;
```