---
title: "Объявление управляемых типов классов | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- __gc types
- classes [C++], managed
- class keyword [C++], CLR
- __value keyword
- value types, declaring
- value keyword [C++]
- managed classes
- interface class keyword
- ref keyword [C++]
ms.assetid: 16de9c94-91d7-492f-8ac7-f0729cc627e9
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: c9e9aba6d2a0485a94385be5b8712d7552261ff1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="declaration-of-a-managed-class-type"></a>Объявление управляемых типов классов
Способ объявления ссылочного типа класса изменилось с управляемых расширений для C++ к Visual C++.  
  
 В управляемых расширениях предшествовало ссылочного типа классов `__gc` ключевое слово. В новом синтаксисе `__gc` ключевое слово заменяется одним из двух составных ключевых слов: `ref class` или `ref struct`. Выбор `struct` или `class` указывает открытые (для `struct`) или private (для `class`) уровень доступа по умолчанию его членов, объявленных в начальном неразмеченном разделе тела типа.  
  
 Аналогичным образом, в управляемых расширениях типу значения классов предшествовало `__value` ключевое слово. В новом синтаксисе `__value` ключевое слово заменяется одним из двух составных ключевых слов: `value class` или `value struct`.  
  
 Тип интерфейса, в управляемых расширениях указывался с помощью ключевого слова `__interface`. В новом синтаксисе оно заменено `interface class`.  
  
 Например следующие объявления класса в управляемых расширениях:  
  
```  
public __gc class Block {};     // reference class  
public __value class Vector {}; // value class  
public __interface IFooBar {};  // interface class  
```  
  
 В новом синтаксисе те же объявления выглядят следующим образом:  
  
```  
public ref class Block {};         // reference class  
public value class Vector {};      // value class  
public interface class IFooBar {}; // interface class  
```  
  
## <a name="specifying-the-class-as-abstract"></a>Определение класса как абстрактный  
 В управляемых расширениях поместить ключевое слово `__abstract` перед `class` ключевое слово (до или после `__gc`) для указания, что класс является неполным и не могут создаваться в рамках программы объектов класса:  
  
```  
public __gc __abstract class Shape {};  
public __gc __abstract class Shape2D: public Shape {};  
```  
  
 В новом синтаксисе укажите `abstract` контекстно-зависимое ключевое слово после имени класса и перед телом класса, базовый класс производным списком или точкой с запятой.  
  
```  
public ref class Shape abstract {};  
public ref class Shape2D abstract : public Shape{};  
```  
  
 Разумеется семантическое значение остается неизменным.  
  
## <a name="specifying-the-class-as-sealed"></a>Определение класса как запечатанный  
 В управляемых расширениях поместить ключевое слово `__sealed` перед `class` ключевое слово (до или после `__gc`) для указания, что объекты класса не может наследоваться из:  
  
```  
public __gc __sealed class String {};  
```  
  
 В новом синтаксисе укажите `sealed` контекстно-зависимое ключевое слово после имени класса и перед телом класса, базовый класс производным списком или точкой с запятой.  
  
 Можно создать производный класс и запечатайте его. Например `String` класс неявно является производным от `Object`. Преимуществом запечатывания класса является поддержка статическое разрешение (то есть во время компиляции) всех вызовов виртуальных функций через запечатанного объекта ссылочного класса. Это вызвано `sealed` спецификатор гарантирует, что `String` дескриптора отслеживания не может ссылаться на производный класс, который предоставляет экземпляр, переопределяющий вызываемый виртуальный метод. Ниже приведен пример запечатанного класса в новом синтаксисе:  
  
```  
public ref class String sealed {};  
```  
  
 Также можно определить класс одновременно как абстрактный и запечатанный - это особое состояние, указывающее статического класса. Это описывается в документации среды CLR следующим образом:  
  
 «Тип, то есть оба `abstract` и `sealed` должны иметь только статические члены и являться тем, что в некоторых языках называется пространством имен.»  
  
 Например вот объявление запечатанного абстрактного класса с использованием синтаксиса управляемых расширений.  
  
```  
public __gc __sealed __abstract class State {  
public:  
   static State() {}  
   static bool inParamList();  
  
private:  
   static bool ms_inParam;  
};  
```  
  
 а вот это объявление, реализованного с использованием нового синтаксиса:  
  
```  
public ref class State abstract sealed {  
public:  
   static State();  
   static bool inParamList();  
  
private:  
   static bool ms_inParam;  
};  
```  
  
## <a name="clr-inheritance-specifying-the-base-class"></a>Наследование среды CLR: Указание базового класса  
 В объектной модели CLR поддерживается только открытое единичное наследование. Однако управляемых расширений сохранить ISO C++ по умолчанию интерпретацию базового класса без ключевого слова доступа указанию закрытого наследования. Это означает, что каждое объявление наследования CLR необходимо было использовать `public` ключевое слово, чтобы переопределить интерпретацию по умолчанию.  
  
```  
// Managed Extensions: error: defaults to private derivation  
__gc class Derived : Base {};  
```  
  
 В определении нового синтаксиса отсутствие ключевого слова доступа указывает открытого наследования в определении наследования среды CLR. Таким образом `public` ключевого слова доступа теперь является необязательным. Хотя это не требует каких-либо изменений управляемых расширений для кода C++, перечислить это изменение для обеспечения полноты.  
  
```  
// New syntax: ok: defaults to public derivation  
ref class Derived : Base{};  
```  
  
## <a name="see-also"></a>См. также  
 [Управляемые типы (C + +/ CL)](../dotnet/managed-types-cpp-cl.md)   
 [Классы и структуры](../windows/classes-and-structs-cpp-component-extensions.md)   
 [abstract](../windows/abstract-cpp-component-extensions.md)   
 [sealed](../windows/sealed-cpp-component-extensions.md)