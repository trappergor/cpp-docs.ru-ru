---
title: Функции шаблонов | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- function templates
- templates, function
- function templates, about function templates
ms.assetid: 59b56a4b-0689-4161-9c07-25021562e2a7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 65d5ed1bae5f4571cad6b942af9d6e9b4ff646ed
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="function-templates"></a>Шаблоны функций
Шаблоны классов определяют семейство связанных классов, основанных на типе аргументов, переданных классу при создании его экземпляра. Шаблоны функций похожи на шаблоны классов, но определяют семейство функций. С помощью шаблонов функций можно задавать наборы функций, основанных на одном коде, но действующих в разных типах или классах. Следующий шаблон функции меняет местами два элемента.  
  
```cpp
// function_templates1.cpp  
template< class T > void MySwap( T& a, T& b ) {  
   T c(a);   
   a = b;   
   b = c;  
}  
int main() {  
}  
```  
  
 Этот код определяет семейство функций, которые меняют местами значения аргументов. На основе этого шаблона, можно создавать функции, меняющие местами **int** и **длинные** типов, а также определяемые пользователем типы. Функция `MySwap` даже меняет местами классы, если правильно определены конструктор копии и оператор присваивания.  
  
 Кроме того, шаблон функции не позволяет разработчику менять местами объекты разных типов, поскольку компилятор во время компиляции знает типы параметров `a` и `b`.  
  
 Хотя эта функция может выполняться нешаблонной функцией с использованием указателей void, версия шаблона типобезопасна. Рассмотрим следующие вызовы:  
  
```cpp
int j = 10;  
int k = 18;  
CString Hello = "Hello, Windows!";  
MySwap( j, k );          //OK  
MySwap( j, Hello );      //error  
```  
  
 Второй вызов `MySwap` приводит к ошибке времени компиляции, поскольку компилятору не удается создать функцию `MySwap` с параметрами разных типов. Если бы использовались указатели void, оба вызова функции скомпилировались бы правильно, но функция не работала бы должным образом во время выполнения.  
  
 Для шаблона функции можно явно задавать аргументы. Пример:  
  
```cpp
// function_templates2.cpp  
template<class T> void f(T) {}  
int main(int j) {  
   f<char>(j);   // Generate the specialization f(char).  
   // If not explicitly specified, f(int) would be deduced.  
}  
```  
  
 Если аргумент шаблона задан явно, выполняются обычные неявные преобразования для преобразования аргумента функции в тип соответствующих параметров шаблона функции. В приведенном выше примере компилятор преобразует `char j` ввода `int`.  
  
## <a name="see-also"></a>См. также  
 [Шаблоны](../cpp/templates-cpp.md)   
 [Создание экземпляра шаблона функции](../cpp/function-template-instantiation.md)   
 [Явное создание экземпляра](../cpp/explicit-instantiation.md)   
 [Явная специализация шаблонов функций](../cpp/explicit-specialization-of-function-templates.md)
