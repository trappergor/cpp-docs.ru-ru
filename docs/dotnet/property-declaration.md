---
title: Объявление свойства | Документация Майкрософт
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
ms.openlocfilehash: 019b8eae17952bfe53fd8fbf14db4bafce1bf463
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46438305"
---
# <a name="property-declaration"></a>Объявление свойства

Способ объявления свойства в управляемом классе отличается от управляемых расширений для C++ в Visual C++.

В управляемых расширениях каждый `set` или `get` метод доступа к свойству задается как независимый метод. Объявление каждого метода добавляется префикс `__property` ключевое слово. Имя метода начинается на `set_` или `get_` следует фактическое имя свойства (как видимый для пользователя). Таким образом `Vector` предоставляя `x` координации `get` бы имя свойства `get_x` и пользователь будет вызывать его как `x`. Это соглашение об именовании и отдельная спецификация методов соответствует базовой реализации свойства среды выполнения. Например, Вот наш `Vector` с набором свойств координат:

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

Это распространяется функциям, связанным со свойством и требует от пользователя лексического объединения связанных наборов и получает. Кроме того он является подробным. В новом синтаксисе, который больше похож на C#, `property` ключевого слова следуют тип свойства и его недекорируемое имя. `set` И `get` методы доступа, помещаются в блоке после имени свойства. Обратите внимание на то, что в отличие от C#, сигнатура метода доступа задан. Например ниже приведен пример кода выше преобразуются в новый синтаксис.

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

Если методы доступа свойства отражают отдельные уровни доступа — например `public get` и `private` или `protected set`, можно указать явную метку доступа. По умолчанию уровень доступа свойства отражает, включающего уровня доступа. Например, в приведенном выше определении метода `Vector`, оба `get` и `set` методы являются `public`. Чтобы сделать `set` метод `protected` или `private`, определение бы переписать следующим образом:

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

Область ключевого слова доступа в пределах свойства распространяется до закрывающей скобки свойства или спецификации ключевого слова доступ к дополнительным возможностям. Она не выходит за определение свойства, включающего уровень доступа, в котором оно определено свойство. В приведенном выше объявлении, `Vector::dot()` открытый метод.

Написание свойств set/get для трех `Vector` координаты состоит из трех этапов:

1. Объявите член закрытого состояния соответствующего типа.

1. возвращается, когда пользователь хочет получить свое значение.

1. Присвойте новое значение.

В новом синтаксисе сокращенный синтаксис свойств доступна который автоматизирует этот шаблон использования:

```
public ref class Vector sealed {
public:
   // equivalent shorthand property syntax
   property double x;
   property double y;
   property double z;
};
```

Интересный побочный эффект сокращенного синтаксиса является то, что несмотря на то, что Backstage-члена создается компилятором, оно не доступно в пределах класса, за исключением через методы доступа set или get.

## <a name="see-also"></a>См. также

[Объявления членов в пределах класса или интерфейса (C++/CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)<br/>
[свойство](../windows/property-cpp-component-extensions.md)