---
title: "Строка (расширения компонентов C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- string support with /clr
- /clr compiler option [C++], string support
ms.assetid: c695f965-9be0-4e20-9661-373bfee6557e
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 3fb87578a0046a70da9a68ab6a1a08b2d6a9f4d1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="string--c-component-extensions"></a>String (расширения компонентов C++)
Компилятор Visual C++ поддерживает *строки*, которые являются объекты, представляющие текст как последовательность знаков. Visual C++ поддерживает строковые переменные с неявными значениями и литералы, значения которых — явные строки в кавычках.  
  
## <a name="all-runtimes"></a>Все среды выполнения  
 Среда выполнения Windows и среда CLR представляют строки в виде объектов, управление выделяемой памятью которых осуществляется автоматически. Это значит, что в случае выхода строковой переменной за пределы области видимости или завершении работы приложения явно отменять память для строки не требуется. Чтобы указать время существования строкового объекта должно осуществляться автоматически, следует объявить тип string с [дескриптор объекта (^)](../windows/handle-to-object-operator-hat-cpp-component-extensions.md) модификатор.  
  
## <a name="windows-runtime"></a>Среда выполнения Windows  
 Архитектура среды выполнения Windows требует от Visual C++ реализации типа данных `String` в пространстве имен `Platform`. Для удобства в Visual C++ также предусмотрен тип данных `string`, являющийся синонимом для `Platform::String` в пространстве имен `default`.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
// compile with /ZW  
using namespace Platform;  
using namespace default;  
   Platform::String^ MyString1 = "The quick brown fox";  
   String^ MyString2 = "jumped over the lazy dog.";  
   String^ MyString3 = "Hello, world!";  
  
```  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения и примеры о строках см. в разделе [Platform::String, std::wstring и литералы (платформы)](http://msdn.microsoft.com/en-us/ec92fbc6-edf3-4137-a85e-8e29bdb857a8)  
  
### <a name="requirements"></a>Требования  
 Параметр компилятора: **/ZW**  
  
## <a name="common-language-runtime"></a>Среда CLR  
 В этом разделе обсуждается, как компилятор Visual C++ обрабатывает строковых литералов при запуске с помощью **/CLR** параметр компилятора. Для использования **/CLR**, необходимо также использовать среду CLR, C + +/ CLI синтаксис и управляемых объектов. Дополнительные сведения о **/CLR**, в разделе [/CLR (компиляция CLR)](../build/reference/clr-common-language-runtime-compilation.md).  
  
 При компиляции с параметром **/CLR**, компилятор преобразует строковые литералы в строки типа <xref:System.String>. Для сохранения обратной совместимости с существующим кодом у этого правила есть два исключения:  
  
-   Обработка исключений. Если появляется строковый литерал, компилятор перехватывает его как строковый литерал.  
  
-   Определение шаблона. Если строковый литерал передается в качестве аргумента шаблона, компилятор не преобразует его в <xref:System.String>. Обратите внимание, что строковые литералы, переданные в качестве универсального аргумента, повышаются до <xref:System.String>.  
  
 В компиляторе также есть встроенная поддержка трех операторов, которые можно переопределять для настройки их поведения:  
  
-   System::String ^ operator +( System::String, System::String);  
  
-   System::String ^ operator +( System::Object, System::String);  
  
-   System::String ^ operator +( System::String, System::Object);  
  
 После передачи <xref:System.String> компилятор при необходимости упаковывает, а затем объединяет объект (с помощью ToString) со строкой.  
  
> [!NOTE]
>  Курсор ("^") означает, что объявленная переменная является дескриптором управляемого объекта C++/CLI.  
  
 Дополнительные сведения см. [строковые и символьные литералы](../cpp/string-and-character-literals-cpp.md).  
  
### <a name="requirements"></a>Требования  
 Параметр компилятора: **/clr**  
  
### <a name="examples"></a>Примеры  
 **Пример**  
  
 В следующем примере кода демонстрируется объединение и сравнение строк.  
  
```cpp  
// string_operators.cpp  
// compile with: /clr  
// In the following code, the caret ("^") indicates that the   
// declared variable is a handle to a C++/CLI managed object.  
using namespace System;  
  
int main() {  
   String ^ a = gcnew String("abc");  
   String ^ b = "def";   // same as gcnew form  
   Object ^ c = gcnew String("ghi");  
  
   char d[100] = "abc";  
  
   // variables of System::String returning a System::String  
   Console::WriteLine(a + b);  
   Console::WriteLine(a + c);  
   Console::WriteLine(c + a);  
  
   // accessing a character in the string  
   Console::WriteLine(a[2]);  
  
   // concatenation of three System::Strings  
   Console::WriteLine(a + b + c);  
  
   // concatenation of a System::String and string literal  
   Console::WriteLine(a + "zzz");  
  
   // you can append to a System::String ^  
   Console::WriteLine(a + 1);  
   Console::WriteLine(a + 'a');  
   Console::WriteLine(a + 3.1);  
  
   // test System::String ^ for equality  
   a += b;  
   Console::WriteLine(a);  
   a = b;  
   if (a == b)  
      Console::WriteLine("a and b are equal");  
  
   a = "abc";  
   if (a != b)  
      Console::WriteLine("a and b are not equal");  
  
   // System:String ^ and tracking reference  
   String^% rstr1 = a;  
   Console::WriteLine(rstr1);  
  
   // testing an empty System::String ^  
   String ^ n;  
   if (n == nullptr)  
      Console::WriteLine("n is empty");  
}  
```  
  
 **Вывод**  
  
```Output  
abcdef  
  
abcghi  
  
ghiabc  
  
c  
  
abcdefghi  
  
abczzz  
  
abc1  
  
abc97  
  
abc3.1  
  
abcdef  
  
a and b are equal  
  
a and b are not equal  
  
abc  
  
n is empty  
```  
  
 **Пример**  
  
 В следующем примере показано, что предоставляемые компилятором операторы можно перегружать, и что компилятор будет искать перегрузку функции на основе типа <xref:System.String>.  
  
```cpp  
// string_operators_2.cpp  
// compile with: /clr  
using namespace System;  
  
// a string^ overload will be favored when calling with a String  
void Test_Overload(const char * a) {   
   Console::WriteLine("const char * a");   
}  
void Test_Overload(String ^ a) {   
   Console::WriteLine("String ^ a");   
}  
  
// overload will be called instead of compiler defined operator  
String ^ operator +(String ^ a, String ^ b) {  
   return ("overloaded +(String ^ a, String ^ b)");  
}  
  
// overload will be called instead of compiler defined operator  
String ^ operator +(Object ^ a, String ^ b) {  
   return ("overloaded +(Object ^ a, String ^ b)");  
}  
  
// overload will be called instead of compiler defined operator  
String ^ operator +(String ^ a, Object ^ b) {  
   return ("overloaded +(String ^ a, Object ^ b)");  
}  
  
int main() {  
   String ^ a = gcnew String("abc");  
   String ^ b = "def";   // same as gcnew form  
   Object ^ c = gcnew String("ghi");  
  
   char d[100] = "abc";  
  
   Console::WriteLine(a + b);  
   Console::WriteLine(a + c);  
   Console::WriteLine(c + a);  
  
   Test_Overload("hello");  
   Test_Overload(d);  
}  
```  
  
 **Вывод**  
  
```Output  
overloaded +(String ^ a, String ^ b)   
  
overloaded +(String ^ a, Object ^ b)   
  
overloaded +(Object ^ a, String ^ b)   
  
String ^ a  
  
const char * a  
```  
  
 **Пример**  
  
 В следующем примере показано, что компилятор различает собственные строки и строки <xref:System.String>.  
  
```cpp  
// string_operators_3.cpp  
// compile with: /clr  
using namespace System;  
int func() {  
   throw "simple string";   // const char *  
};  
  
int func2() {  
   throw "string" + "string";   // returns System::String  
};  
  
template<typename T>  
void func3(T t) {  
   Console::WriteLine(T::typeid);  
}  
  
int main() {  
   try {  
      func();  
   }  
   catch(char * e) {  
      Console::WriteLine("char *");  
   }  
  
   try {  
      func2();  
   }  
   catch(String^ str) {  
      Console::WriteLine("String^ str");  
   }  
  
   func3("string");   // const char *  
   func3("string" + "string");   // returns System::String  
}  
```  
  
 **Вывод**  
  
```Output  
char *  
  
String^ str  
  
System.SByte*  
  
System.String  
```  
  
## <a name="see-also"></a>См. также  
 [Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)   
 [Строковые и символьные литералы](../cpp/string-and-character-literals-cpp.md)   
 [/ CLR (компиляция CLR)](../build/reference/clr-common-language-runtime-compilation.md)