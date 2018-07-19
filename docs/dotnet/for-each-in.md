---
title: для каждой из них в | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::foreach
- for
- each
- in
dev_langs:
- C++
helpviewer_keywords:
- for each keyword [C++]
ms.assetid: 0c3a364b-2747-43f3-bb8d-b7d3b7023f79
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 6ab5f7309da1a037f7066d44815cafc934b162cf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33111947"
---
# <a name="for-each-in"></a>for each, in
Выполняет итерацию по массиву или коллекции. Это нестандартное ключевое слово доступно как в C++/CLI, так и в собственных проектах C++. Однако его использование не рекомендуется. Рассмотрите возможность использования стандартного [инструкции (C++) на основе диапазонов](../cpp/range-based-for-statement-cpp.md) вместо него.  
  
## <a name="all-runtimes"></a>Все среды выполнения  
 **Синтаксис**  
  
```  
  
      for each (typeidentifierinexpression) {  
   statements  
}  
  
```  
  
 **Параметры**  
  
 `type`  
 Тип параметра `identifier`.  
  
 `identifier`  
 Переменная итерации, представляющая элемент коллекции.  Когда `identifier` — [оператор отслеживания ссылок](../windows/tracking-reference-operator-cpp-component-extensions.md), можно изменить элемент.  
  
 `expression`  
 Выражение массива или коллекция. Элемент коллекции должен быть таким, чтобы компилятор мог преобразовать его в тип `identifier`.  
  
 `statements`  
 Один или несколько операторов для выполнения.  
  
 **Заметки**  
  
 Оператор `for each` используется для итерации по коллекции. Можно изменять элементы в коллекции, но добавление или удаление элементов невозможно.  
  
 *Инструкций* выполняются для каждого элемента массива или коллекции. После завершения итерации всех элементов коллекции управление передается следующему оператору после блока `for each`.  
  
 `for each` и `in` , [контекстно-зависимые ключевые слова](../windows/context-sensitive-keywords-cpp-component-extensions.md).  
  
 Дополнительные сведения:  
  
-   [Перебор элементов коллекции стандартной библиотеки C++ с использованием цикла for each](../dotnet/iterating-over-stl-collection-by-using-for-each.md)  
  
-   [Практическое руководство. Перебор элементов массивов с использованием цикла for each](../dotnet/how-to-iterate-over-arrays-with-for-each.md)  
  
-   [Практическое руководство. Перебор элементов универсальной коллекции с использованием цикла for each](../dotnet/how-to-iterate-over-a-generic-collection-with-for-each.md)  
  
-   [Практическое руководство. Перебор элементов определенной пользователем коллекции с использованием цикла for each](../dotnet/how-to-iterate-over-a-user-defined-collection-with-for-each.md)  
  
## <a name="windows-runtime"></a>Среда выполнения Windows  
  
### <a name="requirements"></a>Требования  
 Параметр компилятора: **/ZW**  
  
### <a name="example"></a>Пример  
 В этом примере показано использование `for each` для итерации по строке.  
  
```  
// for_each_string1.cpp  
// compile with: /ZW  
#include <stdio.h>  
using namespace Platform;  
  
ref struct MyClass {  
   property String^ MyStringProperty;  
};  
  
int main() {  
   String^ MyString = ref new String("abcd");  
  
   for each ( char c in MyString )  
      wprintf("%c", c);  
  
   wprintf("/n");  
  
   MyClass^ x = ref new MyClass();  
   x->MyStringProperty = "Testing";  
  
   for each( char c in x->MyStringProperty )  
      wprintf("%c", c);  
}  
```  
  
 **Вывод**  
  
```Output  
abcd  
  
Testing  
```  
  
## <a name="common-language-runtime"></a>Среда CLR 
 **Заметки**  
  
 Синтаксис CLR совпадает со значением **все среды выполнения** синтаксис, за исключением следующего.  
  
 *Выражение*  
 Выражение управляемого массива или коллекция. Элемент коллекции должен быть таким образом, чтобы компилятор мог преобразовать его из <xref:System.Object> для *идентификатор* типа.  
  
 *выражение* результат имеет тип, реализующий <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, или тип, который определяет `GetEnumerator` метод, либо возвращает тип, реализующий <xref:System.Collections.IEnumerator> или объявляет все методы, определенные в `IEnumerator`.  
  
### <a name="requirements"></a>Требования  
 Параметр компилятора: **/clr**  
  
### <a name="example"></a>Пример  
 В этом примере показано использование `for each` для итерации по строке.  
  
```  
// for_each_string2.cpp  
// compile with: /clr  
using namespace System;  
  
ref struct MyClass {  
   property String ^ MyStringProperty;  
};  
  
int main() {  
   String ^ MyString = gcnew String("abcd");  
  
   for each ( Char c in MyString )  
      Console::Write(c);  
  
   Console::WriteLine();  
  
   MyClass ^ x = gcnew MyClass();  
   x->MyStringProperty = "Testing";  
  
   for each( Char c in x->MyStringProperty )  
      Console::Write(c);  
}  
```  
  
 **Вывод**  
  
```Output  
abcd  
  
Testing   
```  
  
## <a name="see-also"></a>См. также  
 [Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)