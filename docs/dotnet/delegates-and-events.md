---
title: "Делегаты и события | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- __event keyword [C++]
- delegate keyword [C++]
- delegates [C++], upgrading from Managed Extensions for C++
- __delegate keyword
- events [C++], upgrading from Managed Extensions for C++
- event keyword [C++]
ms.assetid: 3505c626-7e5f-4492-a947-0e2248f7b84a
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: e332c24d30d0439705b6be5e0748518f6537478d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="delegates-and-events"></a>Делегаты и события
Способ объявления делегатов и событий был изменен с управляемых расширений для C++ к Visual C++.  
  
 Двойной знак подчеркивания больше не нужен, как показано в следующем примере. Ниже приведен пример кода в управляемых расширениях:  
  
```  
__delegate void ClickEventHandler(int, double);  
__delegate void DblClickEventHandler(String*);  
  
__gc class EventSource {  
   __event ClickEventHandler* OnClick;    
   __event DblClickEventHandler* OnDblClick;    
};  
```  
  
 Один и тот же код в новый синтаксис выглядит следующим образом:  
  
```  
delegate void ClickEventHandler( int, double );  
delegate void DblClickEventHandler( String^ );  
  
ref class EventSource {  
   event ClickEventHandler^ OnClick;   
   event DblClickEventHandler^ OnDblClick;   
};  
```  
  
 События (и делегаты) являются ссылочными типами, что определяется в новом синтаксисе из-за использования крышки (`^`).  События, поддержка синтаксис явного объявления и обычная форма, показано в предыдущем примере кода. В явной форме пользователь указывает `add`, `raise`, и `remove` методы, связанные с событием. (Только `add` и `remove` методы являются обязательными; `raise` является необязательным.)  
  
 В управляемых расширениях, если этих методов, также не указано явное объявление события, но необходимо решить, имя события, которое не указан. Каждый метод указывается в виде `add_EventName`, `raise_EventName`, и `remove_EventName`, как показано в следующем примере, взятом из спецификации управляемых расширений:  
  
```  
// explicit implementations of add, remove, raise  
public __delegate void f(int);  
public __gc struct E {  
   f* _E;  
public:  
   E() { _E = 0; }  
  
   __event void add_E1(f* d) { _E += d; }  
  
   static void Go() {  
      E* pE = new E;  
      pE->E1 += new f(pE, &E::handler);  
      pE->E1(17);   
      pE->E1 -= new f(pE, &E::handler);  
      pE->E1(17);   
   }  
  
private:  
   __event void raise_E1(int i) {  
      if (_E)  
         _E(i);  
   }  
  
protected:  
   __event void remove_E1(f* d) {  
      _E -= d;  
   }  
};  
```  
  
 Новый синтаксис простое объявление, как в следующем примере. Указывает событие, два или три метода, заключенный в фигурные скобки и поместить непосредственно после объявления события и его связанный делегат типа, как показано ниже:  
  
```  
public delegate void f( int );  
public ref struct E {  
private:  
   f^ _E; // delegates are also reference types  
  
public:  
   E() {  // note the replacement of 0 with nullptr!  
      _E = nullptr;   
   }  
  
   // the new aggregate syntax of an explicit event declaration  
   event f^ E1 {  
   public:  
      void add( f^ d ) {  
         _E += d;  
      }  
  
   protected:  
      void remove( f^ d ) {  
         _E -= d;  
      }  
  
   private:  
      void raise( int i ) {  
         if ( _E )  
            _E( i );  
      }  
   }  
  
   static void Go() {  
      E^ pE = gcnew E;  
      pE->E1 += gcnew f( pE, &E::handler );  
      pE->E1( 17 );   
      pE->E1 -= gcnew f( pE, &E::handler );  
      pE->E1( 17 );   
   }  
};  
```  
  
## <a name="see-also"></a>См. также  
 [Объявления членов в пределах класса или интерфейса (C + +/ CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 [Delegate (расширения компонентов C++)](../windows/delegate-cpp-component-extensions.md)   
 [event](../windows/event-cpp-component-extensions.md)