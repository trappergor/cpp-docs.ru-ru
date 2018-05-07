---
title: Объявление свойства | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- __property keyword
- declaring properties, C++
- property keyword [C++]
ms.assetid: de169378-a8b8-49f4-a586-76bffc9b5c9f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: bc2cf76384078e579756abe653fb45fd1e97707f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="property-declaration"></a>Объявление свойства
Способ объявления свойства в управляемом классе отличается от управляемых расширений для C++ к Visual C++.  
  
 В управляемых расширениях каждый `set` или `get` указано как независимый метод доступа свойства. Объявление каждого метода добавляется префикс с `__property` ключевое слово. Имя метода начинается с любой `set_` или `get_` следуют фактическое имя свойства (которое отображается для пользователя). Таким образом `Vector` предоставление `x` координации `get` бы имя свойства `get_x` и пользователь будет вызывать его как `x`. Это соглашение вызова и отдельная спецификация методов фактически отражает базовой среды выполнения реализации данного свойства. Например, Вот наш `Vector` с набором свойств координат:  
  
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
  
 Это распространяется функции, связанные со свойством и требует от пользователя лексического объединения связанных наборов и возвращает. Кроме того он является подробным. В новом синтаксисе больше похожи на C#, `property` ключевым словом должны последовать тип свойства и его недекорируемое имя. `set` И `get` методы доступа помещаются в блоке после имени свойства. Обратите внимание, что в отличие от C#, указывается сигнатура метода доступа. Например здесь приведен пример кода выше преобразуется в новый синтаксис.  
  
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
  
 Если методы доступа свойства отражают отдельные уровни доступа — например `public get` и `private` или `protected set`, можно указать явную метку доступа. По умолчанию уровень доступа свойства отражает, включающего его уровня доступа. Например, в приведенном выше определении метода `Vector`, оба `get` и `set` методы являются `public`. Чтобы сделать `set` метод `protected` или `private`, определение нужно переписать следующим образом:  
  
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
  
   } // note: extent of private culminates here  
  
// note: dot is a public method of Vector  
double dot( const Vector^ wv );  
  
// etc.  
};  
```  
  
 Область ключевого слова доступа в пределах свойства распространяется до закрывающей скобки свойства или спецификации с ключевым словом дополнительные права доступа. Он выходит за пределы определение свойства для включающего его уровня доступа, в котором определено свойство. В объявлении выше, например `Vector::dot()` является открытым методом.  
  
 Написание свойств set или get для трех `Vector` координаты состоит из трех этапов:  
  
1.  Объявите член закрытое состояние соответствующего типа.  
  
2.  возвращается, когда пользователь хочет получить свое значение.  
  
3.  Присвойте новое значение.  
  
 В новом синтаксисе сокращенный синтаксис свойств доступен который автоматизирует этот шаблон использования:  
  
```  
public ref class Vector sealed {   
public:  
   // equivalent shorthand property syntax  
   property double x;   
   property double y;  
   property double z;  
};  
```  
  
 Интересный побочный эффект сокращенного синтаксиса является, несмотря на то, что Backstage-члена создается компилятором, он недоступен в пределах класса, за исключением через методы доступа set или get.  
  
## <a name="see-also"></a>См. также  
 [Объявления членов в пределах класса или интерфейса (C + +/ CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 [свойство](../windows/property-cpp-component-extensions.md)