---
title: Ошибка компилятора C3706
ms.date: 11/04/2016
f1_keywords:
- C3706
helpviewer_keywords:
- C3706
ms.assetid: d20a33eb-d625-46c5-ac87-32075a590d07
ms.openlocfilehash: 2d474db5a4d50aed7b59e6f48fb5a3e8165f10c6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50468628"
---
# <a name="compiler-error-c3706"></a>Ошибка компилятора C3706

«функция»: должен быть COM-интерфейс для порождения COM-событий

Интерфейс событий, используемом для порождения COM-событий должен быть COM-интерфейса. В этом случае интерфейс либо должен быть определен с помощью атрибута Visual C++ или импортировать с помощью [#import](../../preprocessor/hash-import-directive-cpp.md) из библиотеки типов с помощью атрибута embedded_idl #import элемента.

Обратите внимание, что `#include` для использования COM-событий необходимы строки файлов заголовков ATL, показано в следующем примере. Чтобы устранить эту ошибку, сделайте `IEvents` (интерфейс событий) COM-интерфейс, применив один из следующих атрибутов к определению интерфейса: [объект](../../windows/object-cpp.md), [двойного](../../windows/dual.md), или [ disp-интерфейс](../../windows/dispinterface.md).

Если интерфейс из файла заголовка, которые генерирует MIDL, компилятор не распознает его как COM-интерфейс.

Следующий пример приводит к возникновению ошибки C3706:

```
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