---
title: "Изменение операторов преобразования | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- conversion operators
- operators [C++], explicit type conversion
- type conversion, explicit conversions
- conversions, explicit
- explicit keyword [C++]
ms.assetid: 9b83925c-71b7-4bd3-ac2e-843dd7c7f184
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 8f89c49035e2e48dde8d502b1d61fa33d198f69a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="changes-to-conversion-operators"></a>Изменение операторов преобразования
Синтаксис операторов преобразования отличается от управляемых расширений для C++ к Visual C++.  
  
 Примером служит для записи `op_Implicit` для указания преобразования. Здесь приведено определение `MyDouble` взяты из спецификации языка:  
  
```  
__gc struct MyDouble {  
   static MyDouble* op_Implicit( int i );   
   static int op_Explicit( MyDouble* val );  
   static String* op_Explicit( MyDouble* val );   
};  
```  
  
 Это говорит, заданного целым числом, алгоритм преобразования целого числа в `MyDouble` обеспечивается `op_Implicit` оператор. Кроме того, что будет выполнено преобразование неявно компилятором. Подобно этому, `MyDouble` двумя `op_Explicit` операторы предоставляют алгоритмы преобразования в целое число или управляемого объекта `String` сущности. Однако компилятор не будет выполнять преобразование, если явно не указано пользователем.  
  
 В C# это выглядит следующим образом:  
  
```  
class MyDouble {  
   public static implicit operator MyDouble( int i );   
   public static explicit operator int( MyDouble val );  
   public static explicit operator string( MyDouble val );   
};  
```  
  
 Код C# выглядит более C++, чем управляемые расширения для C++. Это не так, в новом синтаксисе.  
  
 Комитет ISO-C++ ввел ключевое слово, `explicit`, чтобы избежать непредвиденных последствий - например, `Array` класс, который принимает один целочисленный аргумент, как измерения, неявно преобразует любое целое число в `Array` объекта, который — не требуется. Один из способов предотвращения этого является создание фиктивного второго аргумента конструктора  
  
 С другой стороны не следует предоставлять пару преобразования при разработке типа класса в C++. Лучшим примером этого является класс стандартную строку. Неявное преобразование — конструктор одним аргументом, принимающий строку C-стиле. Тем не менее, он не предоставляет соответствующий неявный оператор преобразования -, для преобразования строкового объекта в строку в стиле языка C, но требует от пользователя явного вызова функции по имени — в этом случае `c_str()`.  
  
 Таким образом появляется связывание явного или неявного поведения в отношении оператора преобразования (и как вложение ряда преобразований в одну форму объявления) представляет собой улучшенную поддержку исходного C++ операторов преобразования, которая привела к `explicit` ключевое слово. Поддержка языка Visual C++ для операторов преобразования выглядит следующим образом и более краткую форму, чем C#, из-за поведение по умолчанию операторов, поддерживающих неявное применение алгоритма преобразования:  
  
```  
ref struct MyDouble {  
public:  
   static operator MyDouble^ ( int i );  
   static explicit operator int ( MyDouble^ val );  
   static explicit operator String^ ( MyDouble^ val );  
};  
```  
  
 Еще одно изменение заключается в том, что единый конструктор аргумента рассматривается как он объявлен как `explicit`. Это означает, что для инициирования его вызова требуется явное приведение. Обратите внимание, что если определен оператор явного преобразования, он и не конструктор одним аргументом может быть вызван.  
  
## <a name="see-also"></a>См. также  
 [Объявления членов в пределах класса или интерфейса (C++/CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)