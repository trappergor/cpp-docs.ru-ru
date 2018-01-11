---
title: "Отражение (C + +/ CLI) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- typeid keyword [C++]
- reflection [C++}, about reflection
- metadata, reflection
- GetType method
- .NET Framework [C++], reflection
- data types [C++], reflection
- reflection [C++}
ms.assetid: 46b6ff4a-e441-4022-8892-78e69422f230
caps.latest.revision: "24"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: fab5bb3c912aeea2598189965d424ba4508cf5c8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="reflection-ccli"></a>Отражение (C++/CLI)
Отражение позволяет известных типов данных необходимо проверить во время выполнения. Отражение позволяет перечисление типов данных в определенной сборке и членов данного типа класса или значения могут быть обнаружены. Это верно независимо от типа был "известен" или "ссылки во время компиляции. Благодаря этому отражение полезной функцией для разработки и средства управления кода.  
  
 Обратите внимание, что предоставленного имени сборки со строгими именами (см. [Создание и использование сборок](/dotnet/framework/app-domains/create-and-use-strong-named-assemblies)), которая содержит версию сборки, язык и региональные параметры и сведения о подписи. Обратите внимание, что имя пространства имен, в которой определен тип данных могут быть извлечены, вместе с именем базового класса.  
  
 Наиболее распространенным способом доступа к функции отражения – <xref:System.Object.GetType%2A> метод. Этот метод предоставляется [System::Object](https://msdn.microsoft.com/en-us/library/system.object.aspx), из которого создаются все классов сбора мусора.  
  
 Отражение на .exe созданного с помощью компилятора Visual C++ допускается только в том случае, если .exe, созданного с помощью **/CLR: pure** или **/CLR: safe** параметры компилятора. Параметры компилятора **/CLR: pure** и **/CLR: safe** в Visual Studio 2015 не рекомендуется использовать. В разделе [/CLR (компиляция CLR)](../build/reference/clr-common-language-runtime-compilation.md) для получения дополнительной информации.  
  
 Подразделы в этом разделе:  
  
-   [Практическое руководство. Реализация архитектуры с подключаемыми компонентами с помощью отражения (C++/CLI)](../dotnet/how-to-implement-a-plug-in-component-architecture-using-reflection-cpp-cli.md)  
  
-   [Практическое руководство. Перечисление типов данных в сборках с помощью отражения (C++/CLI)](../dotnet/how-to-enumerate-data-types-in-assemblies-using-reflection-cpp-cli.md)  
  
 Дополнительные сведения см. в разделе [пространства имен System.Reflection](https://msdn.microsoft.com/en-us/library/system.reflection.aspx)  
  
## <a name="example"></a>Пример  
 `GetType` Метод возвращает указатель на <xref:System.Type> объект класса, который описывает тип после при основан объект. ( **Тип** объект не содержит все сведения, относящиеся к экземпляру.) Один элемент — полное имя типа, который выглядит следующим образом:  
  
 Обратите внимание, что имя типа включает полную область, в которой определен тип, включая пространство имен, и что он отображается в синтаксисе .NET с точкой как оператор разрешения области.  
  
```  
// vcpp_reflection.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   String ^ s = "sample string";  
   Console::WriteLine("full type name of '{0}' is '{1}'", s, s->GetType());  
}  
```  
  
```Output  
full type name of 'sample string' is 'System.String'  
```  
  
## <a name="example"></a>Пример  
 Типы значений, которые можно использовать с `GetType` также работать, но они должны быть упакованы сначала.  
  
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
  
```Output  
type of i = 'System.Int32'  
```  
  
## <a name="example"></a>Пример  
 Как и в `GetType` метода [typeid](../windows/typeid-cpp-component-extensions.md) оператор возвращает указатель на **тип** объекта, поэтому этот код указывает имя типа **System.Int32**. Отображение имен типов является основным для отражения, но является более полезным для проверки или обнаружения действительных значений для перечислимых типов. Это можно сделать с помощью статического **Enum::GetNames** функцию, которая возвращает массив строк, каждая из которых содержит значение перечисления в виде текста.  Следующий пример возвращает массив строк, который описывает значения перечисления для **параметры** перечисления (CLR), которые отображаются в цикле.  
  
 Если четвертый параметр добавляется **параметры** перечисления, код сообщит о новом параметре без повторной компиляции, даже если перечисление определено в отдельной сборке.  
  
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
  
```Output  
there are 3 options in enum 'Options'  
0: Option1  
1: Option2  
2: Option3  
value of 'o' is Option2  
```  
  
## <a name="example"></a>Пример  
 `GetType` Объект поддерживает несколько элементов и свойств, которые могут использоваться для проверки типа. Этот код извлекает и отображает некоторые из этих сведений.  
  
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
  
```Output  
type information for 'String':  
assembly name: mscorlib, Version=1.0.5000.0, Culture=neutral,   
PublicKeyToken=b77a5c561934e089  
namespace: System  
base type: System.Object  
is array: False  
is class: True  
```  
  
## <a name="example"></a>Пример  
 Отражение также разрешает перечисление типов в сборки и членов в классы. Чтобы продемонстрировать эту функцию, определите простой класс:  
  
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
  
## <a name="example"></a>Пример  
 Если приведенный выше код компилируется в DLL с именем vcpp_reflection_6.dll, можно затем использовать отражение для проверки содержимого этой сборки. При этом используется статическое отражение функции API [Assembly::Load](https://msdn.microsoft.com/en-us/library/system.reflection.assembly.load.aspx) для загрузки сборки. Эта функция возвращает адрес **сборки** объект, который можно запросить о типах и модулях.  
  
 Как только система отражения успешно загружает сборку, массив **тип** получить объектов с [Assembly::GetTypes](https://msdn.microsoft.com/en-us/library/system.reflection.assembly.gettypes.aspx) функции. Каждый элемент массива содержит сведения об определенном типе, хотя в этом случае определен только один класс. С помощью цикла, каждый **тип** в этом массиве отправляется запрос об элементах типа **Type::GetMembers** функции. Эта функция возвращает массив **MethodInfo** объектов, каждый объект, содержащий сведения о функции-члена, член данных или свойство в типе.  
  
 Примечание список методов включает функции явно определенных в **TestClass** и функции неявно наследуется от **System::Object** класса. В рамках описываемого в .NET, а не в синтаксисе Visual C++ свойства отображаются как базовому элементу данных, доступ к функции get и set. В этом списке отображаются функций get и set, как обычные методы. Отражение поддерживается через CLR, не компилятором Visual C++.  
  
 Несмотря на то, что этот код используется для проверки сборки, которое было определено, также можно использовать для этого кода исследовать сборки .NET. Например при изменении TestAssembly на библиотеку mscorlib, будет просмотреть список все типы и метод, определенный в mscorlib.dll.  
  
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
  
## <a name="see-also"></a>См. также  
 [Программирование .NET с использованием C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)