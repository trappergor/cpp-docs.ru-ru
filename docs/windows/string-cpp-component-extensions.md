---
title: "String (расширения компонентов C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/clr - параметр компилятора [C++], поддержка строк"
  - "поддержка строк с использованием /clr"
ms.assetid: c695f965-9be0-4e20-9661-373bfee6557e
caps.latest.revision: 19
caps.handback.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# String (расширения компонентов C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Компилятор Visual C\+\+ поддерживает *строки*, являющиеся объектами, которые представляют текст как последовательность символов.  Visual C\+\+ поддерживает строковые переменные, значения которых являются неявными, и литералы, значением которых является явная строка в кавычках.  
  
## Все среды выполнения  
 Среда выполнения Windows и среда CLR представляют строки как объекты, чья выделяемая память управляется автоматически.  Это значит, что не требуется явно отменять память для строки, если переменная выходит за пределы области видимости или приложение завершается.  Чтобы указать, что время существования объекта строки должно управляться автоматически, объявите тип string с помощью модификатора [дескриптор\-объекта \(^\)](../windows/handle-to-object-operator-hat-cpp-component-extensions.md).  
  
## среда выполнения Windows  
 Архитектура среды выполнения Windows требует Visual C\+\+ реализовывать тип данных `String` в пространстве имен `Platform`.  Для удобства Visual C\+\+ также предоставляет тип данных `string`, синоним для `Platform::String` в пространстве имен `default`.  
  
### Синтаксис  
  
```cpp  
  
// compile with /ZW  
using namespace Platform;  
using namespace default;  
   Platform::String^ MyString1 = "The quick brown fox";  
   String^ MyString2 = "jumped over the lazy dog.";  
   String^ MyString3 = "Hello, world!";  
  
```  
  
### Примечания  
 Дополнительные сведения и примеры со строками см. в разделе [Platform::String, std::wstring, and Literals \(Platform\)](http://msdn.microsoft.com/ru-ru/ec92fbc6-edf3-4137-a85e-8e29bdb857a8).  
  
### Требования  
 Параметр компилятора: **\/ZW**  
  
## Среда CLR  
 В этом разделе рассматривается, как компилятор Visual C\+\+ обрабатывает строковые литералы при запуске с помощью параметра компилятора **\/clr**.  Для использования **\/clr**, необходимо использовать среду CLR, синтаксис C\+\+\/CLI и управляемые объекты.  Дополнительные сведения о **\/clr** см. в разделе [\/clr \(компиляция CLR\)](../build/reference/clr-common-language-runtime-compilation.md).  
  
 При компилировании с **\/clr**, компилятор преобразует строковые литералы в строки типа <xref:System.String>.  Для сохранения обратной совместимости с существующим кодом есть два исключения:  
  
-   Обработка исключений.  Если возникает строковый литерал, компилятор будет перехватывать его как строковый литерал.  
  
-   Вывод шаблона.  Если строковый литерал передается в качестве аргумента шаблона, компилятор не преобразует его в <xref:System.String>.  Обратите внимание, что строковые литералы, переданные как универсальный аргумент, будут повышены до <xref:System.String>.  
  
 Компилятор также имеет встроенную поддержку трех операторов, которые можно переопределить для изменения их поведения.  
  
-   System::String ^ operator \+\( System::String, System::String\);  
  
-   System::String ^ operator \+\( System::Object, System::String\);  
  
-   System::String ^ operator \+\( System::String, System::Object\);  
  
 После передачи <xref:System.String>, компилятор будет упаковывать, если необходимо, а затем сцеплять объект \(с ToString\) со строкой.  
  
 При компилировании с **\/clr:oldSyntax**, строковые литералы не будут преобразованы в <xref:System.String>.  
  
> [!NOTE]
>  Курсор \("^"\) означает, что объявленная переменная является дескриптором управляемого объекта C\+\+\/CLI.  
  
 Дополнительные сведения см. в разделе [Строковые и символьные литералы](../cpp/string-and-character-literals-cpp.md).  
  
### Требования  
 Параметр компилятора: **\/clr**  
  
### Примеры  
 **Пример**  
  
 В следующем примере кода демонстрируется сцепление и сравнение строк.  
  
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
  
 **Output**  
  
  **abcdef**  
 **abcghi**  
 **ghiabc**  
 **c**  
 **abcdefghi**  
 **abczzz**  
 **abc1**  
 **abc97**  
 **abc3.1**  
 **abcdef**  
 **a и b равны**  
 **a и b не равны**  
 **abc**  
 **n пусто** **Пример**  
  
 В следующем примере показано, что можно перегружать предоставленные компилятором операции, и что компилятор будет искать перегрузку функции на основе типа <xref:System.String>.  
  
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
  
 **Output**  
  
  **overloaded \+\(String ^ a, String ^ b\)**   
 **overloaded \+\(String ^ a, Object ^ b\)**   
 **overloaded \+\(Object ^ a, String ^ b\)**   
 **String ^ a**  
 **const char \* a** **Пример**  
  
 Следующий пример демонстрирует, что компилятор делает различия между собственными строками и строками <xref:System.String>.  
  
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
  
 **Output**  
  
  **char \***  
 **String^ str**  
 **System.SByte\***  
 **System.String**   
## См. также  
 [Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)   
 [Строковые и символьные литералы](../cpp/string-and-character-literals-cpp.md)   
 [\/clr \(компиляция CLR\)](../build/reference/clr-common-language-runtime-compilation.md)