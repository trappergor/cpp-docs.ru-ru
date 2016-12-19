---
title: "Объявление свойства | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__property - ключевое слово"
  - "объявление свойств, C++"
  - "property - ключевое слово [C++]"
ms.assetid: de169378-a8b8-49f4-a586-76bffc9b5c9f
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Объявление свойства
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)] изменился способ объявления свойства в управляемом классе по сравнению с управляемыми расширениями C\+\+.  
  
 В управляемых расширениях каждый метод доступа свойства `set` или `get` задается как независимый метод.  К объявлению каждого метода добавляется префикс — ключевое слово `__property`.  Имя метода начинается на `set_` или `get_`, после чего следует фактическое имя свойства \(которое видит пользователь\).  Таким образом, метод `Vector`, предоставляющий свойство `get` координаты `x`, будет именовать это свойство `get_x`, а пользователь будет вызывать его как `x`.  Это соглашение вызова и отдельная спецификация методов фактически отражают основную реализацию свойства во время выполнения.  Для примера ниже приведен наш метод `Vector` с набором свойств координат.  
  
```  
public __gc __sealed class Vector {  
public:  
   __property double get_x(){ return _x; }  
   __property double get_y(){ return _y; }  
   __property double get_z(){ return _z; }  
  
   __property void set_x( double newx ){ _x = newx; }  
   __property void set_y( double newy ){ _y = newy; }  
   __property void set_z( double newz ){ _z = newz; }  
};  
```  
  
 Этот метод распределяет функциональные возможности, связанные со свойством, и требует от пользователя лексического объединения связанных свойств set и get.  Кроме того, он является подробным.  В новом синтаксисе, который больше напоминает синтаксис C\#, за ключевым словом `property` следует тип свойства и его недекорируемое имя.  Методы доступа `set` и `get` помещаются в блоке после имени свойства.  Обратите внимание: в отличие от C\#, здесь указывается сигнатура метода доступа.  В качестве примера ниже показан приведенный выше код, преобразованный в новый синтаксис.  
  
```  
public ref class Vector sealed {   
public:  
   property double x {  
      double get() {  
         return _x;  
      }  
  
      void set( double newx ) {  
         _x = newx;  
      }  
   } // Note: no semi-colon  
};  
```  
  
 Если методы доступа свойства отражают отдельные уровни доступа, например `public` `get` и `private` или `protected` `set`, можно указать явную метку доступа.  По умолчанию уровень доступа свойства соответствует включающему его уровню.  Например, в приведенном выше определении метода `Vector` методы `get` и `set` имеют уровень `public`.  Чтобы назначить методу `set` уровень `protected` или `private`, определение нужно переписать следующим образом.  
  
```  
public ref class Vector sealed {   
public:  
   property double x {  
      double get() {  
         return _x;  
      }  
  
   private:  
      void set( double newx ) {  
         _x = newx;  
      }  
  
   } // note: extent of private culminates here …  
  
// note: dot is a public method of Vector  
double dot( const Vector^ wv );  
  
// etc.  
};  
```  
  
 Область действия ключевого слова доступа в пределах свойства распространяется до закрывающей скобки свойства либо до дополнительного ключевого слова доступа.  Область действия не выходит за рамки определения свойства для включающего его уровня доступа, в котором определено это свойство.  Например, в объявлении выше `Vector::dot()` является открытым методом.  
  
 Написание свойств set\/get для трех координат `Vector` включает три стадии.  
  
1.  Объявление закрытого члена соответствующего типа.  
  
2.  Возвращение этого члена по желанию пользователя.  
  
3.  Присваивание ему нового значения.  
  
 В новом синтаксисе доступен сокращенный синтаксис свойств, который позволяет автоматизировать данную модель использования.  
  
```  
public ref class Vector sealed {   
public:  
   // equivalent shorthand property syntax  
   property double x;   
   property double y;  
   property double z;  
};  
```  
  
 Интересным побочным эффектом этого сокращенного синтаксиса является недоступность backstage\-члена в классе \(за исключением доступа через методы set\/get\), несмотря на то, что он создается компилятором.  
  
## См. также  
 [Объявления членов в пределах класса или интерфейса \(C\+\+\/CLI\)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 [property](../windows/property-cpp-component-extensions.md)