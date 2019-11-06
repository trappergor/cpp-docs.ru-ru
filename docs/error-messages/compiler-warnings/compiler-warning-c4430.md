---
title: Предупреждение компилятора C4430
ms.date: 11/04/2016
f1_keywords:
- C4430
helpviewer_keywords:
- C4430
ms.assetid: 12efbfff-aa58-4a86-a7d6-2c6a12d01dd3
ms.openlocfilehash: 661b687373d6c72b9f40a05d1406bc89ce332133
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/05/2019
ms.locfileid: "73623706"
---
# <a name="compiler-warning-c4430"></a>Предупреждение компилятора C4430

отсутствует спецификатор типа — предполагается int. Примечание. C++ не поддерживает int по умолчанию

Эта ошибка может быть вызвана работой по согласованности компилятора, выполненной для Visual Studio 2005: все объявления должны явно указывать тип. int больше не предполагается.

C4430 всегда выдается как ошибка.  Это предупреждение можно отключить с помощью `#pragma warning` или **/WD**; Дополнительные сведения см. в разделе [warning](../../preprocessor/warning.md) или [/w,/W0,/W1,/W2,/W3,/W4,/W1,/W2,/W3,/W4,/Wall,/WD,/We,/WO,/WV,/WX (уровень предупреждений)](../../build/reference/compiler-option-warning-level.md) .

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4430.

```cpp
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