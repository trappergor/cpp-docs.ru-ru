---
title: "for each, in | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::foreach"
  - "for"
  - "each"
  - "in"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "for each - ключевое слово [C++]"
ms.assetid: 0c3a364b-2747-43f3-bb8d-b7d3b7023f79
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# for each, in
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Выполняет итерацию по массиву или коллекции.  Это нестандартное ключевое слово доступно как в C\+\+\/CLI, так и в собственных проектах C\+\+.  Однако его использование не рекомендуется.  Вместо этого рекомендуется использовать стандартный [Основанное на диапазоне выражение for \(C\+\+\)](../Topic/Range-based%20for%20Statement%20\(C++\).md).  
  
## Все среды выполнения  
 **Синтаксис**  
  
```  
  
        for each (type identifier in expression) {  
   statements  
}  
  
```  
  
 **Параметры**  
  
 `type`  
 Тип параметра `identifier`.  
  
 `identifier`  
 Переменная итерации, представляющая элемент коллекции.  Если `identifier` представляет собой [Оператор отслеживания ссылок](../windows/tracking-reference-operator-cpp-component-extensions.md), этот элемент можно изменять.  
  
 `expression`  
 Выражение массива или коллекция.  Элемент коллекции должен быть таким, чтобы компилятор мог преобразовать его в тип `identifier`.  
  
 `statements`  
 Один или несколько операторов для выполнения.  
  
 **Заметки**  
  
 Оператор `for each` используется для итерации по коллекции.  Можно изменять элементы в коллекции, но добавление или удаление элементов невозможно.  
  
 *statements* выполняются для каждого элемента массива или коллекции.  После завершения итерации всех элементов коллекции управление передается следующему оператору после блока `for each`.  
  
 `for each` и `in` — это [контекстно\-зависимые ключевые слова](../windows/context-sensitive-keywords-cpp-component-extensions.md).  
  
 Дополнительные сведения:  
  
-   [Перебор элементов коллекции STL с использованием цикла for each](../dotnet/iterating-over-stl-collection-by-using-for-each.md)  
  
-   [Практическое руководство. Перебор элементов массивов с использованием цикла for each](../dotnet/how-to-iterate-over-arrays-with-for-each.md)  
  
-   [Практическое руководство. Перебор элементов универсальной коллекции с использованием цикла for each](../dotnet/how-to-iterate-over-a-generic-collection-with-for-each.md)  
  
-   [Практическое руководство. Перебор элементов определенной пользователем коллекции с использованием цикла for each](../Topic/How%20to:%20Iterate%20Over%20a%20User-Defined%20Collection%20with%20for%20each.md)  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
  
### Требования  
 Параметр компилятора: **\/ZW**  
  
### Пример  
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
  
 **Выходные данные**  
  
  **abcd**  
 **Testing**   
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 **Заметки**  
  
 Синтаксис CLR совпадает с синтаксисом для **всех сред выполнения**, за исключением следующего.  
  
 *expression*  
 Выражение управляемого массива или коллекция.  Элемент коллекции должен быть таким, чтобы компилятор мог преобразовать его из <xref:System.Object> в тип *identifier*.  
  
 Результат вычисления *expression* представляет собой тип, реализующий <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, или тип, определяющий метод `GetEnumerator`, который либо возвращает тип, реализующий <xref:System.Collections.IEnumerator>, либо объявляет все методы, определенные в `IEnumerator`.  
  
### Требования  
 Параметр компилятора: **\/clr**  
  
### Пример  
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
  
 **Выходные данные**  
  
  **abcd**  
 **Testing**    
## См. также  
 [Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)