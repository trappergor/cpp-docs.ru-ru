---
title: "Ошибка компилятора C3706 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3706
dev_langs: C++
helpviewer_keywords: C3706
ms.assetid: d20a33eb-d625-46c5-ac87-32075a590d07
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 20f7e14d22e1994213624d88ccab098844aa6ac4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3706"></a>Ошибка компилятора C3706
«функция»: должен быть COM-интерфейса для порождения COM-событий  
  
 Интерфейс событий, который используется для порождения COM-событий должен быть COM-интерфейса. В этом случае интерфейса должны быть определены с использованием атрибута Visual C++ или импортировать с помощью [#import](../../preprocessor/hash-import-directive-cpp.md) из библиотеки типов с атрибутом embedded_idl #import элемента.  
  
 Обратите внимание, что `#include` для использования COM-событий необходимы строки файлов заголовков ATL, представленные в примере ниже. Чтобы устранить эту ошибку, `IEvents` (интерфейс событий) COM-интерфейс, применив один из следующих атрибутов к определению интерфейса: [объекта](../../windows/object-cpp.md), [двойного](../../windows/dual.md), или [ disp-интерфейса](../../windows/dispinterface.md).  
  
 Если интерфейс из заголовка файла, созданного MIDL, компилятор не распознает его как COM-интерфейса.  
  
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