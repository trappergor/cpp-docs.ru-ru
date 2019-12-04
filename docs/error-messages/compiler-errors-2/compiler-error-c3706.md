---
title: Ошибка компилятора C3706
ms.date: 11/04/2016
f1_keywords:
- C3706
helpviewer_keywords:
- C3706
ms.assetid: d20a33eb-d625-46c5-ac87-32075a590d07
ms.openlocfilehash: 810ec59a814b04349913648fb49a03eb63912cd9
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757986"
---
# <a name="compiler-error-c3706"></a>Ошибка компилятора C3706

"функция": должен быть COM-интерфейсом для запуска COM-событий

Интерфейс событий, используемый для запуска COM-событий, должен быть COM-интерфейсом. В этом случае интерфейс должен либо быть определен с помощью визуального C++ атрибута, либо импортирован с помощью [#import](../../preprocessor/hash-import-directive-cpp.md) из библиотеки типов с атрибутом #import embedded_idl.

Обратите внимание, что `#include` строки файлов заголовков ATL, показанные в примере ниже, необходимы для использования COM-событий. Чтобы устранить эту ошибку, сделайте `IEvents` (интерфейс событий) COM-интерфейсом, применив к определению интерфейса один из следующих атрибутов: [объект](../../windows/object-cpp.md), [двойной](../../windows/dual.md)или [интерфейсный](../../windows/dispinterface.md)интерфейс.

Если интерфейс получен из файла заголовка, созданного с помощью MIDL, компилятор не сможет распознать его как COM-интерфейс.

Следующий пример приводит к возникновению ошибки C3706:

```cpp
// C3706.cpp
// compile with: /c
// C3706 expected
#define _ATL_ATTRIBUTES 1
#include <atlbase.h>
#include <atlcom.h>
#include <atlctl.h>

[module(dll, name="idid", uuid="12341234-1234-1234-1234-123412341234")];

// Uncomment the following line to resolve.
// [object, uuid="12341234-1234-1234-1234-123412341237"]
__interface IEvents : IUnknown {
   HRESULT event1(/*[in]*/ int i);   // uncomment [in]
};

[dual, uuid="12341234-1234-1234-1234-123412341235"]
__interface IBase {
   HRESULT fireEvents();
};

[coclass, event_source(com), uuid="12341234-1234-1234-1234-123412341236"]
class CEventSrc : public IBase {
   public:
   __event __interface IEvents;

   HRESULT fireEvents() {
      HRESULT hr = IEvents_event1(123);
      return hr;
   }
};
```
