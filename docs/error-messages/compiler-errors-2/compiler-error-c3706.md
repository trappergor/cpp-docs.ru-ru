---
title: Ошибка компилятора C3706
ms.date: 11/04/2016
f1_keywords:
- C3706
helpviewer_keywords:
- C3706
ms.assetid: d20a33eb-d625-46c5-ac87-32075a590d07
ms.openlocfilehash: 461850b2c1686343f23c77274b8fb2ca6fd9071e
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91508012"
---
# <a name="compiler-error-c3706"></a>Ошибка компилятора C3706

"функция": должен быть COM-интерфейсом для запуска COM-событий

Интерфейс событий, используемый для запуска COM-событий, должен быть COM-интерфейсом. В этом случае интерфейс должен либо быть определен с помощью атрибута Visual C++, либо импортирован с помощью [#import](../../preprocessor/hash-import-directive-cpp.md) из библиотеки типов с атрибутом embedded_idl #import.

Обратите внимание, что `#include` строки файлов заголовков ATL, показанные в приведенном ниже примере, необходимы для использования COM-событий. Чтобы устранить эту ошибку, сделайте `IEvents` (интерфейс событий) COM-интерфейс, применив к определению интерфейса один из следующих атрибутов: [Object](../../windows/attributes/object-cpp.md), [Dual](../../windows/attributes/dual.md)или [DISP](../../windows/attributes/dispinterface.md).

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
