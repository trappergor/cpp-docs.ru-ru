---
title: "Делегаты и события | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__delegate - ключевое слово"
  - "__event - ключевое слово [C++]"
  - "delegate - ключевое слово [C++]"
  - "делегаты [C++], обновление с управляемых расширений для C++"
  - "event - ключевое слово [C++]"
  - "события [C++], обновление с управляемых расширений для C++"
ms.assetid: 3505c626-7e5f-4492-a947-0e2248f7b84a
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Делегаты и события
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

По сравнению с управляемыми расширениями для C\+\+, в [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)] изменен порядок объявления делегатов и событий.  
  
 Как показано в следующем примере, синтаксис с двойным подчеркиванием более не используется.  Ниже приведен пример кода для управляемых расширений:  
  
```  
__delegate void ClickEventHandler(int, double);  
__delegate void DblClickEventHandler(String*);  
  
__gc class EventSource {  
   __event ClickEventHandler* OnClick;    
   __event DblClickEventHandler* OnDblClick;    
};  
```  
  
 При использовании нового синтаксиса этот пример выглядит следующим образом:  
  
```  
delegate void ClickEventHandler( int, double );  
delegate void DblClickEventHandler( String^ );  
  
ref class EventSource {  
   event ClickEventHandler^ OnClick;   
   event DblClickEventHandler^ OnDblClick;   
};  
```  
  
 События и делегаты представляют собой ссылочные типы, что определяется в новом синтаксисе с помощью знака крышки \(`^`\).  Для событий поддерживается синтаксис явного объявления, а также обычная форма объявления, показанная в предыдущем примере.  В явной форме необходимо определить связанные с событием методы `add`, `raise` и `remove`. Методы `add` и `remove` являются обязательными. Метод `raise` является необязательным.  
  
 В управляемых расширениях при объявлении этих методов не требуется использовать явное объявление события, однако необходимо указать имя события.  Методы определяются в форме `add_EventName`, `raise_EventName` и `remove_EventName`, как показано в следующем примере, представленном в спецификации управляемых расширений:  
  
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
  
 В новом синтаксисе используется более простое объявление, показанное в следующем примере.  Необходимые методы определяются в фигурных скобках непосредственно после объявления события и связанного с ним типа делегата, как показано ниже:  
  
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
  
## См. также  
 [Объявления членов в пределах класса или интерфейса \(C\+\+\/CLI\)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 [delegate](../windows/delegate-cpp-component-extensions.md)   
 [event](../windows/event-cpp-component-extensions.md)