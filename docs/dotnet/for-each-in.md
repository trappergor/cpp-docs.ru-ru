---
title: для каждого из них в | Документация Майкрософт
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
ms.openlocfilehash: a55425c891999142fe32ae08125cce22728daffa
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46040701"
---
# <a name="for-each-in"></a>for each, in
Выполняет итерацию по массиву или коллекции. Это нестандартное ключевое слово доступно как в C++/CLI, так и в собственных проектах C++. Однако его использование не рекомендуется. Рекомендуется использовать стандартный [по диапазону для инструкции (C++)](../cpp/range-based-for-statement-cpp.md) вместо этого.  
  
## <a name="all-runtimes"></a>Все среды выполнения  
 **Синтаксис**  
  
```  
  
      for each (typeidentifierinexpression) {  
   statements  
}  
  
```  
  
 **Параметры**  
  
*type*<br/>
Тип параметра `identifier`.  
  
*identifier*<br/>
Переменная итерации, представляющая элемент коллекции.  Когда `identifier` — [оператор отслеживания ссылок](../windows/tracking-reference-operator-cpp-component-extensions.md), этот элемент можно изменять.  
  
*Выражение*<br/>
Выражение массива или коллекция. Элемент коллекции должен быть таким, чтобы компилятор мог преобразовать его в тип `identifier`.  
  
*Инструкции*<br/>
Один или несколько операторов для выполнения.  
  
 **Заметки**  
  
 Оператор `for each` используется для итерации по коллекции. Можно изменять элементы в коллекции, но добавление или удаление элементов невозможно.  
  
 *Инструкций* выполняются для каждого элемента в массиве или коллекции. После завершения итерации всех элементов коллекции управление передается следующему оператору после блока `for each`.  
  
 `for each` и `in` являются [контекстно-зависимые ключевые слова](../windows/context-sensitive-keywords-cpp-component-extensions.md).  
  
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
  
 *выражение* результат имеет тип, реализующий <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, или тип, который определяет `GetEnumerator` метод, который либо возвращает тип, реализующий <xref:System.Collections.IEnumerator> или объявляет все методы, которые определены в `IEnumerator`.  
  
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