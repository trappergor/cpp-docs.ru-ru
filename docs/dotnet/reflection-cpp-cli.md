---
title: Отражение (C + +/ CLI) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- typeid keyword [C++]
- reflection [C++}, about reflection
- metadata, reflection
- GetType method
- .NET Framework [C++], reflection
- data types [C++], reflection
- reflection [C++}
- plug-ins [C++]
- reflection [C++}, plug-ins
- assemblies [C++], enumerating data types in
- public types [C++]
- reflection [C++], external assemblies
- assemblies [C++]
- data types [C++], enumerating
- public members [C++]
ms.assetid: 46b6ff4a-e441-4022-8892-78e69422f230
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: af227712e3ac64d69836f5cf83b6629bdbffe834
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46432730"
---
# <a name="reflection-ccli"></a>Отражение (C++/CLI)

Отражение позволяет известных типов данных проверять во время выполнения. Отражение позволяет перечисление типов данных в определенной сборке и элементы заданного типа класса или значения могут быть обнаружены. Это верно независимо от того, этот тип был "известен" или "указывается во время компиляции. В результате отражения полезная функция для разработки и средства управления кода.

Обратите внимание, что предоставленного имени сборки строгим именем (см. в разделе [Создание и использование сборок со строгими именами](/dotnet/framework/app-domains/create-and-use-strong-named-assemblies)), который включает версию сборки, язык и региональные параметры и сведения о подписи. Кроме того, обратите внимание, что имя пространства имен, в котором определен тип данных можно извлечь, вместе с именем базового класса.

Наиболее распространенным способом доступа к функции отражения – <xref:System.Object.GetType%2A> метод. Этот метод предоставляется [System::Object](https://msdn.microsoft.com/library/system.object.aspx), из которого все сборщиком мусора классы являются производными.

> [!NOTE]
> Отражение на созданного с помощью компилятора Visual C++ .exe допускается только в том случае, если .exe построен с использованием **/CLR: pure** или **/CLR: safe** параметры компилятора. **/CLR: pure** и **/CLR: safe** параметры компилятора: не рекомендуется в Visual Studio 2015 и недоступна в Visual Studio 2017. См. в разделе [/CLR (компиляция CLR)](../build/reference/clr-common-language-runtime-compilation.md) Дополнительные сведения.

Дополнительные сведения см. в разделе [пространства имен System.Reflection](https://msdn.microsoft.com/library/system.reflection.aspx)

## <a name="example-gettype"></a>Пример: GetType

`GetType` Метод возвращает указатель на <xref:System.Type> объект класса, который описывает тип на при основано объекта. ( **Тип** объект не содержит все сведения, относящиеся к экземпляру.) Одна из них — полное имя типа, которое может отображаться следующим образом:

Обратите внимание, что имя типа включает полную область, в котором определен тип, включая пространство имен, и что он отображается в синтаксисе .NET с точкой как оператор разрешения области.

```cpp
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

## <a name="example-boxed-value-types"></a>Пример: упакованных типов значений

Типы значений можно использовать с `GetType` также работать, но они должны быть упакованы сначала.

```cpp
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

## <a name="example-typeid"></a>Пример: typeid

Как и в `GetType` метод, [typeid](../windows/typeid-cpp-component-extensions.md) оператор возвращает указатель на **тип** объекта, поэтому этот код указывает имя типа **System.Int32**. Отображение имен типов — это самый простой функции отражения, но потенциально более полезный прием — для проверки или обнаружения действительных значений для перечислимых типов. Это можно сделать с помощью статического **Enum::GetNames** функцию, которая возвращает массив строк, каждая из которых содержит значение перечисления в виде текста.  Следующий пример возвращает массив строк, описывающих значения перечисления для **параметры** enum (CLR) и отображает их в цикле.

Если добавляется четвертый вариант **параметры** перечисления, этот код будет о новом параметре без повторной компиляции, даже если перечисление определено в отдельной сборке.

```cpp
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

## <a name="example-gettype-members-and-properties"></a>Пример: GetType элементов и свойств

`GetType` Объект поддерживает несколько элементов и свойств, которые могут использоваться для проверки типа. Этот код извлекает и отображает часть этой информации:

```cpp
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

## <a name="example-enumeration-of-types"></a>Пример: перечисление типов

Отражение также разрешает перечисление типов в сборки и членов в классах. Чтобы продемонстрировать эту функцию, определите простой класс:

```cpp
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

## <a name="example-inspection-of-assemblies"></a>Пример: проверка сборок

Если приведенный выше код компилируется в DLL с именем vcpp_reflection_6.dll, можно затем использовать отражение для проверки содержимого этой сборки. При этом используется статическое отражение функции API [Assembly::Load](https://msdn.microsoft.com/library/system.reflection.assembly.load.aspx) для загрузки сборки. Эта функция возвращает адрес **сборки** объект, который можно запросить о типах и модулях.

Как только система отражения успешно загружает сборку, массив **тип** объектов возвращается с помощью [Assembly::GetTypes](https://msdn.microsoft.com/library/system.reflection.assembly.gettypes.aspx) функции. Каждый элемент массива содержит сведения о другой тип, несмотря на то, что в этом случае определяется только один класс. С помощью цикла, каждый **тип** в этом массиве отправляется запрос об элементах типа **Type::GetMembers** функции. Эта функция возвращает массив **MethodInfo** объектов, каждый объект, содержащий сведения о функции-члена, данные-член или свойство в типе.

Обратите внимание, что список методов включает функции явно определенных в **TestClass** и функции, неявно наследуется от **System::Object** класса. В рамках описываемого в .NET, а не в синтаксисе Visual C++ свойства отображаются как базового члена данных, которому принадлежит функций get и set. В этом списке отображаются функций get и set, как обычные методы. Отражение поддерживается через CLR, не с помощью компилятора Visual C++.

Несмотря на то, что вы использовали этот код для проверки сборки, которое было определено, можно также использовать этот код для проверки сборок .NET. Например при изменении TestAssembly на библиотеку mscorlib, вы увидите список каждого типа и метод, определенный в библиотеке mscorlib.dll.

```cpp
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

## <a name="implement"></a> Практическое: реализация архитектуры с подключаемыми компонентами с помощью отражения

В следующих примерах кода демонстрируется использование отражения для реализации простой архитектуры «подключаемого модуля». Первый листинг — это приложение, а второй — подключаемый модуль. Приложение является формой нескольких документов, которые заполняются с помощью любой форм классы, находящиеся в библиотеку DLL подключаемого модуля, предоставляется как аргумент командной строки.

Приложение пытается загрузить сборки, используя предоставленное <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> метод. Если в случае успешного выполнения типы в сборке перечисляются с помощью <xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=fullName> метод. Каждый тип затем проверяется на совместимость с помощью <xref:System.Type.IsAssignableFrom%2A?displayProperty=fullName> метод. В этом примере классов, содержащихся в предоставленной сборке должен быть производным от <xref:System.Windows.Forms.Form> класса было определено как подключаемый модуль.

Затем совместимые классы создаются с помощью <xref:System.Activator.CreateInstance%2A?displayProperty=fullName> метод, который принимает <xref:System.Type> как аргумент и возвращает указатель на новый экземпляр. Каждый новый экземпляр затем присоединяться к форме и отображается.

Обратите внимание, что <xref:System.Reflection.Assembly.Load%2A> метод не принимает имена сборок, которые включают расширение файла. Функция main в приложении удаляет любые предоставленные расширения, поэтому в следующем примере кода работает в любом случае.

### <a name="example"></a>Пример

Следующий код определяет приложение, которое принимает подключаемые модули. Имя сборки необходимо указать в качестве первого аргумента. Эта сборка должна содержать по крайней мере один открытый <xref:System.Windows.Forms.Form> производный тип.

```cpp
// plugin_application.cpp
// compile with: /clr /c
#using <system.dll>
#using <system.drawing.dll>
#using <system.windows.forms.dll>

using namespace System;
using namespace System::Windows::Forms;
using namespace System::Reflection;

ref class PluggableForm : public Form  {
public:
   PluggableForm() {}
   PluggableForm(Assembly^ plugAssembly) {
      Text = "plug-in example";
      Size = Drawing::Size(400, 400);
      IsMdiContainer = true;

      array<Type^>^ types = plugAssembly->GetTypes( );
      Type^ formType = Form::typeid;

      for (int i = 0 ; i < types->Length ; i++) {
         if (formType->IsAssignableFrom(types[i])) {
            // Create an instance given the type description.
            Form^ f = dynamic_cast<Form^> (Activator::CreateInstance(types[i]));
            if (f) {
               f->Text = types[i]->ToString();
               f->MdiParent = this;
               f->Show();
            }
         }
      }
   }
};

int main() {
   Assembly^ a = Assembly::LoadFrom("plugin_application.exe");
   Application::Run(gcnew PluggableForm(a));
}
```

### <a name="example"></a>Пример

Следующий код определяет три класса, производного от <xref:System.Windows.Forms.Form>. Если результирующее имя сборки передается к исполняемому файлу в предыдущем примере, каждый из этих трех классов будет обнаружен и создан, несмотря на то, что все они неизвестны ведущему приложению во время компиляции.

```cpp
// plugin_assembly.cpp
// compile with: /clr /LD
#using <system.dll>
#using <system.drawing.dll>
#using <system.windows.forms.dll>

using namespace System;
using namespace System::Windows::Forms;
using namespace System::Reflection;
using namespace System::Drawing;

public ref class BlueForm : public Form {
public:
   BlueForm() {
      BackColor = Color::Blue;
   }
};

public ref class CircleForm : public Form {
protected:
   virtual void OnPaint(PaintEventArgs^ args) override {
      args->Graphics->FillEllipse(Brushes::Green, ClientRectangle);
   }
};

public ref class StarburstForm : public Form {
public:
   StarburstForm(){
      BackColor = Color::Black;
   }
protected:
   virtual void OnPaint(PaintEventArgs^ args) override {
      Pen^ p = gcnew Pen(Color::Red, 2);
      Random^ r = gcnew Random( );
      Int32 w = ClientSize.Width;
      Int32 h = ClientSize.Height;
      for (int i=0; i<100; i++) {
         float x1 = w / 2;
         float y1 = h / 2;
         float x2 = r->Next(w);
         float y2 = r->Next(h);
         args->Graphics->DrawLine(p, x1, y1, x2, y2);
      }
   }
};
```

## <a name="enumerate"></a> Практическое: перечисление типов данных в сборках с помощью отражения

В следующем коде показано перечисление открытых типов и членов с помощью <xref:System.Reflection>.

Заданному имени сборки, в локальном каталоге или в глобальном кэше СБОРОК, приведенный ниже код пытается открыть ее и получить описания. В случае успешного выполнения каждого типа отображается с открытым членам.

Обратите внимание, что <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> требует, чтобы использовалась без расширения файла. Таким образом используя в качестве аргумента командной строки «mscorlib.dll» завершится ошибкой, пока просто «mscorlib» приведет к Отображение типов .NET Framework. Если имя сборки не указано, код будет обнаруживать и сообщающих типы в текущей сборке (EXE-файл из этого кода).

### <a name="example"></a>Пример

```cpp
// self_reflection.cpp
// compile with: /clr
using namespace System;
using namespace System::Reflection;
using namespace System::Collections;

public ref class ExampleType {
public:
   ExampleType() {}
   void Func() {}
};

int main() {
   String^ delimStr = " ";
   array<Char>^ delimiter = delimStr->ToCharArray( );
   array<String^>^ args = Environment::CommandLine->Split( delimiter );

// replace "self_reflection.exe" with an assembly from either the local
// directory or the GAC
   Assembly^ a = Assembly::LoadFrom("self_reflection.exe");
   Console::WriteLine(a);

   int count = 0;
   array<Type^>^ types = a->GetTypes();
   IEnumerator^ typeIter = types->GetEnumerator();

   while ( typeIter->MoveNext() ) {
      Type^ t = dynamic_cast<Type^>(typeIter->Current);
      Console::WriteLine("   {0}", t->ToString());

      array<MemberInfo^>^ members = t->GetMembers();
      IEnumerator^ memberIter = members->GetEnumerator();
      while ( memberIter->MoveNext() ) {
         MemberInfo^ mi = dynamic_cast<MemberInfo^>(memberIter->Current);
         Console::Write("      {0}", mi->ToString( ) );
         if (mi->MemberType == MemberTypes::Constructor)
            Console::Write("   (constructor)");

         Console::WriteLine();
      }
      count++;
   }
   Console::WriteLine("{0} types found", count);
}
```

## <a name="see-also"></a>См. также

- [Программирование .NET с использованием C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)
