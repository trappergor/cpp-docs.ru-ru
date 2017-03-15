---
title: "Отражение (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/13/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".NET Framework [C++], отражение"
  - "типы данных [C++], отражение"
  - "GetType - метод"
  - "метаданные, отражение"
  - "отражение [C++]"
  - "отражение [C++], об отражении"
  - "typeid - ключевое слово [C++]"
ms.assetid: 46b6ff4a-e441-4022-8892-78e69422f230
caps.latest.revision: 24
caps.handback.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Отражение (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Отражение позволяет осуществлять проверку известных типов данных во время выполнения.  Отражение также разрешает перечисление типов данных в определенной сборке для обнаружения заданного класса или типа значения.  Это не зависит от того, был ли тип известным во время компиляции или была ли на него установлена ссылка.  Благодаря этому отражение является полезной функцией для инструментов разработки и управления кодом.  
  
 Обратите внимание, что предоставляемое имя сборки должно быть строгим \(см. раздел [Сборки со строгими именами](../Topic/Creating%20and%20Using%20Strong-Named%20Assemblies.md)\) и включать версию сборки, язык и региональные параметры, а также сведения о подписях.  Также следует иметь в виду, что можно извлечь имя пространства имен, в котором определен тип данных, вместе с именем базового класса.  
  
 Наиболее распространенным способом доступа к функции отражения является использование метода <xref:System.Object.GetType%2A>.  Этот метод предоставляется классом [System::Object](https://msdn.microsoft.com/en-us/library/system.object.aspx), от которого происходят все классы сборки мусора.  
  
 Отражение EXE\-файла, построенного с помощью компилятора Visual C\+\+, разрешено, если при его построении использовались параметры компилятора **\/clr:pure** или **\/clr:safe**.  Дополнительные сведения см. в разделе [\/clr \(компиляция CLR\)](../build/reference/clr-common-language-runtime-compilation.md).  
  
 Подразделы в этом разделе:  
  
-   [Практическое руководство. Реализация архитектуры с подключаемыми компонентами с помощью отражения](../dotnet/how-to-implement-a-plug-in-component-architecture-using-reflection-cpp-cli.md)  
  
-   [Практическое руководство. Перечисление типов данных в сборках с помощью отражения](../dotnet/how-to-enumerate-data-types-in-assemblies-using-reflection-cpp-cli.md)  
  
 Дополнительные сведения см. в разделе [Пространство имен System.Reflection](https://msdn.microsoft.com/en-us/library/system.reflection.aspx)  
  
## Пример  
 Метод `GetType` возвращает указатель на объект класса <xref:System.Type>, описывающий тип, на котором основан объект. \(Объект **Type** не содержит сведений о конкретных экземплярах.\) Такой элемент является полным именем типа, который выглядит следующим образом.  
  
 Обратите внимание, что имя типа включает полную область действия, в которой определен тип, включая пространство имен. В синтаксисе .NET оно отображается с пикселем как оператор разрешения области действия.  
  
```  
// vcpp_reflection.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   String ^ s = "sample string";  
   Console::WriteLine("full type name of '{0}' is '{1}'", s, s->GetType());  
}  
```  
  
  **full type name of 'sample string' is 'System.String'**   
## Пример  
 Типы значения также можно использовать с функцией `GetType`, но сначала они должны быть упакованы.  
  
```  
// vcpp_reflection_2.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   Int32 i = 100;   
   Object ^ o = i;  
   Console::WriteLine("type of i = '{0}'", o->GetType());  
}  
```  
  
  **тип i \= 'System.Int32'**   
## Пример  
 Так же как и метод `GetType`, оператор [typeid](../Topic/typeid%20%20\(C++%20Component%20Extensions\).md) возвращает указатель на объект **Type**, поэтому код указывает имя типа **System.Int32**.  Отображение имен типов является одной из основных функций отражения, однако более полезным является выполнение проверки или обнаружения действительных значений для перечисленных типов.  Это можно осуществить с помощью статической функции **Enum::GetNames**, которая возвращает массив строк, каждая из которых содержит значение перечисления в текстовом формате.  В следующем примере показано извлечение массива строк, описывающих значения перечисления для перечисления **Options** \(CLR\), и их отображение в цикле.  
  
 Если четвертый параметр добавляется к перечислению **Options**, код сообщит о новом параметре без повторной компиляции, даже если перечисление определено в отдельной сборке.  
  
```  
// vcpp_reflection_3.cpp  
// compile with: /clr  
using namespace System;  
  
enum class Options {   // not a native enum  
   Option1, Option2, Option3  
};  
  
int main() {  
   array<String^>^ names = Enum::GetNames(Options::typeid);  
  
   Console::WriteLine("there are {0} options in enum '{1}'",   
               names->Length, Options::typeid);  
  
   for (int i = 0 ; i < names->Length ; i++)  
      Console::WriteLine("{0}: {1}", i, names[i]);  
  
   Options o = Options::Option2;  
   Console::WriteLine("value of 'o' is {0}", o);  
}  
```  
  
  **В перечислении "Параметры" есть три варианта**  
**0: Option1**  
**1: Option2**  
**2: Option3**  
**Значение "o" — Option2**   
## Пример  
 Объект `GetType` поддерживает несколько элементов и свойств, которые могут быть использованы для проверки типа.  В данном коде извлекаются и отображаются некоторые из этих сведений:  
  
```  
// vcpp_reflection_4.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   Console::WriteLine("type information for 'String':");  
   Type ^ t = String::typeid;  
  
   String ^ assemblyName = t->Assembly->FullName;  
   Console::WriteLine("assembly name: {0}", assemblyName);  
  
   String ^ nameSpace = t->Namespace;  
   Console::WriteLine("namespace: {0}", nameSpace);  
  
   String ^ baseType = t->BaseType->FullName;  
   Console::WriteLine("base type: {0}", baseType);  
  
   bool isArray = t->IsArray;  
   Console::WriteLine("is array: {0}", isArray);  
  
   bool isClass = t->IsClass;  
   Console::WriteLine("is class: {0}", isClass);  
}  
```  
  
  **сведения о типе "Строка":**  
**assembly name: mscorlib, Version\=1.0.5000.0, Culture\=neutral,**   
**PublicKeyToken\=b77a5c561934e089**  
**пространство имен: System**  
**base type: System.Object**  
**is array: False**  
**is class: True**   
## Пример  
 Отражение также разрешает перечисление типов в сборке, а элементов — в классах.  Чтобы продемонстрировать эту функцию, определим простой класс:  
  
```  
// vcpp_reflection_5.cpp  
// compile with: /clr /LD  
using namespace System;  
public ref class TestClass {  
   int m_i;  
public:  
   TestClass() {}  
   void SimpleTestMember1() {}  
   String ^ SimpleMember2(String ^ s) { return s; }   
   int TestMember(int i) { return i; }  
   property int Member {  
      int get() { return m_i; }  
      void set(int i) { m_i = i; }  
   }  
};  
```  
  
## Пример  
 Если приведенный код компилируется в библиотеку DLL с именем Vcpp\_reflection\_6.dll, можно использовать отражение для проверки содержимого этой сборки.  При этом используется статическое отражение функции API [Assembly::Load](https://msdn.microsoft.com/en-us/library/system.reflection.assembly.load.aspx) для загрузки сборки.  Эта функция возвращает адрес объекта **Assembly**, куда можно отправлять запросы о вложенных типах и модулях.  
  
 Как только система отражения выполнит загрузку сборки, с помощью функции [Assembly::GetTypes](https://msdn.microsoft.com/en-us/library/system.reflection.assembly.gettypes.aspx) извлекается массив объектов **Type**.  Каждый элемент массива содержит сведения об определенном типе, хотя в данном случае определен только один класс.  Используя функцию **Type::GetMembers** в цикле, каждому объекту **Type** в массиве отправляется запрос об элементах типа.  Данная функция возвращает массив объектов **MethodInfo**, каждый из которых содержит сведения о функции\-члене, элементе данных или свойстве в типе.  
  
 Обратите внимание, что в список методов включены функции, явно определенные в **TestClass**, а также функции, неявно унаследованные от класса **System::Object**.  Поскольку свойства описаны частично с помощью синтаксиса .NET, а не Visual C\+\+, они представляются как базовый элемент данных, используемый функциями get\/set.  Функции get\/set в этом списке отображаются как обычные методы.  Отражение поддерживается средой CLR, но не поддерживается компилятором Visual C\+\+.  
  
 Хотя данный код использовался для проверки определенной пользователем сборки, его также можно использовать для проверки сборок .NET.  Например, если заменить "TestAssembly" на "Mscorlib", то будет отображаться перечень всех типов и методов, определенных в Mscorlib.dll.  
  
```  
// vcpp_reflection_6.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::IO;  
using namespace System::Reflection;  
int main() {  
   Assembly ^ a = nullptr;  
   try {  
      // load assembly -- do not use file extension  
      // will look for .dll extension first  
      // then .exe with the filename  
      a = Assembly::Load("vcpp_reflection_5");  
   }  
   catch (FileNotFoundException ^ e) {  
      Console::WriteLine(e->Message);  
      return -1;  
   }  
  
   Console::WriteLine("assembly info:");  
   Console::WriteLine(a->FullName);  
   array<Type^>^ typeArray = a->GetTypes();  
  
   Console::WriteLine("type info ({0} types):", typeArray->Length);  
  
   int totalTypes = 0;  
   int totalMembers = 0;  
   for (int i = 0 ; i < typeArray->Length ; i++) {  
      // retrieve array of member descriptions  
      array<MemberInfo^>^ member = typeArray[i]->GetMembers();  
  
      Console::WriteLine("  members of {0} ({1} members):",   
      typeArray[i]->FullName, member->Length);  
      for (int j = 0 ; j < member->Length ; j++) {  
         Console::Write("       ({0})",   
         member[j]->MemberType.ToString() );  
         Console::Write("{0}  ", member[j]);  
         Console::WriteLine("");  
         totalMembers++;  
      }  
      totalTypes++;  
   }  
   Console::WriteLine("{0} total types, {1} total members",  
   totalTypes, totalMembers);  
}  
```  
  
## См. также  
 [программирование .NET с использованием C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)