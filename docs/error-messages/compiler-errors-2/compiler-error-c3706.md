---
title: "Ошибка компилятора C3706 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3706"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3706"
ms.assetid: d20a33eb-d625-46c5-ac87-32075a590d07
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Ошибка компилятора C3706
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"функция": для порождения COM\-событий должен быть COM\-интерфейсом  
  
 Интерфейс событий, используемый для порождения COM\-событий, должен быть интерфейсом COM.  В этой ситуации интерфейс должен либо задаваться с использованием атрибута Visual C\+\+, либо импортироваться с использованием команды [\#import](../Topic/%23import%20Directive%20\(C++\).md) из библиотеки типов с атрибутом импорта embedded\_idl.  
  
 Имейте в виду, что для использования COM\-событий необходимы строки `#include` файлов заголовков ATL, представленные в примере ниже.  Для устранения этой ошибки преобразуйте `IEvents` \(интерфейс событий\) в COM\-интерфейс, применив один из следующих атрибутов к определению интерфейса: [object](../Topic/object%20\(C++\).md), [dual](../Topic/dual.md) или [dispinterface](../../windows/dispinterface.md).  
  
 Если интерфейс построен из файла заголовков, созданного MIDL, компилятор не распознает его как COM\-интерфейс.  
  
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