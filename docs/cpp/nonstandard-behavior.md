---
title: "Нестандартное поведение | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- compatibility and compliance, nonstandard behavior
- Microsoft-specific, compiler behavior
- nonstandard behavior, compliance and compatibility
ms.assetid: a57dea27-dc79-4f64-8a83-017e84841773
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 13420db99afa801d02306f4dd8af4104ec322bd5
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="nonstandard-behavior"></a>Нестандартное поведение
В следующих разделах представлены некоторые ситуации, когда реализация Visual C++ кода C++ не соответствует стандарту C++. Приведенные ниже номера разделов соответствуют номерам разделов в стандарте C++ 11 (ISO/IEC 14882:2011(E)).  
  
 Список ограничений компилятора, отличающихся от указанных в стандарте C++, приведен [ограничения компилятора](../cpp/compiler-limits.md).  
  
## <a name="covariant-return-types"></a>Ковариантные типы возвращаемого значения  
 Виртуальные базовые классы не поддерживаются в качестве ковариантных возвращаемых типов, если виртуальная функция имеет виртуальное число аргументов. Это не соответствует пункту 7 раздела 10.3 спецификации C++ ISO. Следующий пример не компилируется, выдается ошибка компилятора [C2688](../error-messages/compiler-errors-2/compiler-error-c2688.md)  
  
```cpp  
// CovariantReturn.cpp  
class A   
{  
   virtual A* f(int c, ...);   // remove ...  
};  
  
class B : virtual A  
{  
   B* f(int c, ...);   // C2688 remove ...  
};  
```  
  
## <a name="binding-nondependent-names-in-templates"></a>Привязка независимых имен в шаблонах  
 В настоящее время компилятор Visual C++ не поддерживает привязку независимых имен при первоначальном синтаксическом анализе шаблона. Это не соответствует разделу 14.6.3 спецификации C++ ISO. Это может привести к тому, что перегруженные версии, объявленные после шаблона (но до создания его экземпляра), будут видны.  
  
```cpp  
#include <iostream>  
using namespace std;  
  
namespace N {  
   void f(int) { cout << "f(int)" << endl;}  
}  
  
template <class T> void g(T) {  
    N::f('a');   // calls f(char), should call f(int)  
}  
  
namespace N {  
    void f(char) { cout << "f(char)" << endl;}  
}  
  
int main() {  
    g('c');  
}  
// Output: f(char)  
  
```  
  
## <a name="function-exception-specifiers"></a>Описатели исключений функций  
 Описатели исключений функции, отличные от `throw()`, анализируются, но не используются. Это не соответствует разделу 15.4 спецификации C++ ISO. Пример:  
  
```cpp  
void f() throw(int); // parsed but not used  
void g() throw();    // parsed and used  
```  
  
 Дополнительные сведения о спецификациях исключений см. в разделе [спецификации исключений](../cpp/exception-specifications-throw-cpp.md).  
  
## <a name="chartraitseof"></a>char_traits::eof()  
 Стандартные состояния C++, [char_traits::eof](../standard-library/char-traits-struct.md#eof) не должны соответствовать допустимому `char_type` значение. Компилятор Visual C++ принудительно вводит это ограничение для типа `char`, но не для типа `wchar_t`. Это не соответствует требованиям в таблице 62 в разделе 12.1.1 спецификации ISO C++. Это демонстрируется в приведенном ниже примере.  
  
```cpp  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
  
    char_traits<char>::int_type int2 = char_traits<char>::eof();  
    cout << "The eof marker for char_traits<char> is: " << int2 << endl;  
  
    char_traits<wchar_t>::int_type int3 = char_traits<wchar_t>::eof();  
    cout << "The eof marker for char_traits<wchar_t> is: " << int3 << endl;  
}  
```  
  
## <a name="storage-location-of-objects"></a>Место хранения объектов  
 Стандарт языка C++ (раздел 1.8, пункт 6) требует, чтобы полные объекты C++ имели уникальные расположения хранения. Однако в Visual C++ C в некоторых случаях типы без данных-членов хранятся в одном расположении совместно с другими типами в течение времени существования объекта.
