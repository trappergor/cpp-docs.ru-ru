---
title: Управляемые типы (C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- data types [C++], managed
- managed data types [C++]
- .NET Framework [C++], managed types
- data types [C++], .NET feature access
- main function, in managed applications
- managed code, main() function
- .NET Framework [C++], C++ equivalents
- __nogc type declarations
- __value keyword, issues when nesting
- equality, testing for
- versioning, diagnosing conflicts
- versioning
- exceptions, diagnosing odd behavior
- compatibility, between assemblies
ms.assetid: 679b8ed3-d966-4a0c-b627-2a3f3ec96b74
ms.openlocfilehash: c542151bda780e5306db35049d988e6514fffd62
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225609"
---
# <a name="managed-types-ccli"></a>Управляемые типы (C++/CLI)

Visual C++ предоставляет доступ к функциям .NET через управляемые типы, которые обеспечивают поддержку функций среды CLR и подвержены преимуществам и ограничениям среды выполнения.

## <a name="managed-types-and-the-main-function"></a><a name="main_functions"></a>Управляемые типы и функция Main

При написании приложения с помощью **`/clr`** аргументы функции **Main ()** не могут иметь управляемый тип.

Пример правильной сигнатуры:

```cpp
// managed_types_and_main.cpp
// compile with: /clr
int main(int, char*[], char*[]) {}
```

## <a name="net-framework-equivalents-to-c-native-types"></a><a name="dotnet"></a>.NET Framework эквиваленты машинным типам C++

В следующей таблице показаны ключевые слова для встроенных типов Visual C++, которые являются псевдонимами предопределенных типов в пространстве имен **System** .

|Тип Visual C++|Тип платформы .NET Framework|
|-----------------------|-------------------------|
|**`void`**|<xref:System.Void?displayProperty=nameWithType>|
|**`bool`**|<xref:System.Boolean?displayProperty=nameWithType>|
|**`signed char`** |<xref:System.SByte?displayProperty=nameWithType>|
|**`unsigned char`**|<xref:System.Byte?displayProperty=nameWithType>|
|**`wchar_t`**|<xref:System.Char?displayProperty=nameWithType>|
|**`short`** и **`signed short`**|<xref:System.Int16?displayProperty=nameWithType>|
|**`unsigned short`**|<xref:System.UInt16?displayProperty=nameWithType>|
|**`int`**, **`signed int`** , **`long`** и**`signed long`**|<xref:System.Int32?displayProperty=nameWithType>|
|**`unsigned int`** и **`unsigned long`**|<xref:System.UInt32?displayProperty=nameWithType>|
|**`__int64`** и **`signed __int64`**|<xref:System.Int64?displayProperty=nameWithType>|
|**`unsigned __int64`**|<xref:System.UInt64?displayProperty=nameWithType>|
|**`float`**|<xref:System.Single?displayProperty=nameWithType>|
|**`double`** и **`long double`**|<xref:System.Double?displayProperty=nameWithType>|

Дополнительные сведения о параметре компилятора, который по умолчанию **`signed char`** имеет значение или **`unsigned char`** , см. в разделе [ `/J` (тип по умолчанию **`char`** — **`unsigned`** )](../build/reference/j-default-char-type-is-unsigned.md).

## <a name="version-issues-for-value-types-nested-in-native-types"></a><a name="version_issues"></a>Проблемы с версиями для типов значений, вложенных в собственные типы

Рассмотрим подписанный (строгое имя) компонент сборки, используемый для сборки клиентской сборки. Компонент содержит тип значения, который используется в клиенте как тип для члена собственного объединения, класса или массива. Если в следующей версии компонента изменяется размер или структура типа значения, клиент должен быть перекомпилирован.

Создайте файл ключа с [sn.exe](/dotnet/framework/tools/sn-exe-strong-name-tool) ( `sn -k mykey.snk` ).

### <a name="example"></a>Пример

Ниже приведен пример компонента.

```cpp
// nested_value_types.cpp
// compile with: /clr /LD
using namespace System::Reflection;
[assembly:AssemblyVersion("1.0.0.*"),
assembly:AssemblyKeyFile("mykey.snk")];

public value struct S {
   int i;
   void Test() {
      System::Console::WriteLine("S.i = {0}", i);
   }
};
```

### <a name="example"></a>Пример

Этот пример является клиентом:

```cpp
// nested_value_types_2.cpp
// compile with: /clr
#using <nested_value_types.dll>

struct S2 {
   S MyS1, MyS2;
};

int main() {
   S2 MyS2a, MyS2b;
   MyS2a.MyS1.i = 5;
   MyS2a.MyS2.i = 6;
   MyS2b.MyS1.i = 10;
   MyS2b.MyS2.i = 11;

   MyS2a.MyS1.Test();
   MyS2a.MyS2.Test();
   MyS2b.MyS1.Test();
   MyS2b.MyS2.Test();
}
```

### <a name="output"></a>Выходные данные

```Output
S.i = 5
S.i = 6
S.i = 10
S.i = 11
```

### <a name="comments"></a>Комментарии

Однако если добавить `struct S` в nested_value_types. cpp другой член, (например, `double d;` ) и выполнить повторную компиляцию компонента без перекомпиляции клиента, результатом будет необработанное исключение (типа <xref:System.IO.FileLoadException?displayProperty=fullName> ).

## <a name="how-to-test-for-equality"></a><a name="test_equality"></a>Руководство. Проверка на равенство

В следующем примере проверка на равенство, использующую управляемые расширения для C++, зависит от того, на что ссылаются дескрипторы.

### <a name="example"></a>Пример

```cpp
// mcppv2_equality_test.cpp
// compile with: /clr /LD
using namespace System;

bool Test1() {
   String ^ str1 = "test";
   String ^ str2 = "test";
   return (str1 == str2);
}
```

IL для этой программы показывает, что возвращаемое значение реализуется с помощью вызова op_Equality.

```MSIL
IL_0012:  call       bool [mscorlib]System.String::op_Equality(string,
                                                               string)
```

## <a name="how-to-diagnose-and-fix-assembly-compatibility-problems"></a><a name="diagnose_fix"></a>Как диагностировать и исправить проблемы совместимости сборок

В этом разделе объясняется, что может произойти, если версия сборки, на которую ссылается время компиляции, не совпадает с версией сборки, на которую ссылается среда выполнения, и как избежать этой проблемы.

При компиляции сборки можно ссылаться на другие сборки с помощью `#using` синтаксиса. Во время компиляции доступ к этим сборкам осуществляется компилятором. Сведения из этих сборок используются для принятия решений по оптимизации.

Однако если сборка, на которую указывает ссылка, изменена и перекомпилирована, и не выполняется повторная компиляция ссылающейся сборки, которая зависит от нее, сборки могут быть несовместимыми. Решения по оптимизации, которые были действительными на первый, могут быть неправильными по отношению к новой версии сборки. В связи с этими несовместимостью могут возникать различные ошибки времени выполнения. В таких случаях нет конкретного исключения, которое будет создано. Способ, которым ошибка сообщается во время выполнения, зависит от характера изменения кода, вызвавшего проблему.

Эти ошибки не должны быть проблемой в окончательном рабочем коде, если все приложение будет перестроено для выпущенной версии продукта. Сборки, выпускаемые в общедоступной версии, должны быть помечены официальной версией, что позволит избежать этих проблем. Дополнительные сведения см. в разделе [Версии сборок](/dotnet/framework/app-domains/assembly-versioning).

### <a name="diagnosing-and-fixing-an-incompatibility-error"></a>Диагностика и устранение ошибки несовместимости

1. Если возникли исключения среды выполнения или другие условия ошибок, возникающие в коде, который ссылается на другую сборку и не имеют другой идентифицированной причины, возможно, вы работаете с устаревшей сборкой.

1. Сначала следует изолировать и воспроизвести исключение или другое условие ошибки. Проблема, возникающая из-за устаревшего исключения, должна быть воспроизводимой.

1. Проверьте метку времени всех сборок, на которые ссылается ваше приложение.

1. Если метки времени для сборок, на которые имеются ссылки, позже, чем метка времени последней компиляции приложения, то приложение устарело. Если это происходит, перекомпилируйте приложение с последней сборкой и внесите необходимые изменения в код.

1. Перезапустите приложение, выполните действия, которые воспроизводят проблему, и убедитесь, что исключение не возникает.

### <a name="example"></a>Пример

Следующая программа иллюстрирует проблему, уменьшая доступность метода и пытаясь получить доступ к этому методу в другой сборке без перекомпиляции. Попробуйте сначала выполнить компиляцию `changeaccess.cpp` . Это связанная сборка, которая будет изменена. Затем скомпилируйте `referencing.cpp` . Компиляция выполнена с ошибкой. Теперь Сократите доступность вызываемого метода. Перекомпилируйте `changeaccess.cpp` с флагом `/DCHANGE_ACCESS` . Это делает метод защищенным, а не закрытым, чтобы его можно было использовать по закону. Без `referencing.exe` повторной компиляции перезапустите приложение. <xref:System.MethodAccessException>Будет получено исключение.

```cpp
// changeaccess.cpp
// compile with: /clr:safe /LD
// After the initial compilation, add /DCHANGE_ACCESS and rerun
// referencing.exe to introduce an error at runtime. To correct
// the problem, recompile referencing.exe

public ref class Test {
#if defined(CHANGE_ACCESS)
protected:
#else
public:
#endif

  int access_me() {
    return 0;
  }

};
```

```cpp
// referencing.cpp
// compile with: /clr:safe
#using <changeaccess.dll>

// Force the function to be inline, to override the compiler's own
// algorithm.
__forceinline
int CallMethod(Test^ t) {
  // The call is allowed only if access_me is declared public
  return t->access_me();
}

int main() {
  Test^ t = gcnew Test();
  try
  {
    CallMethod(t);
    System::Console::WriteLine("No exception.");
  }
  catch (System::Exception ^ e)
  {
    System::Console::WriteLine("Exception!");
  }
  return 0;
}
```

## <a name="see-also"></a>См. также статью

[Программирование .NET с использованием C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)<br/>
[Совместимость с другими языками .NET (C++/CLI)](../dotnet/interoperability-with-other-dotnet-languages-cpp-cli.md)<br/>
[Управляемые типы (C++/CLI)](../dotnet/managed-types-cpp-cli.md)<br/>
[Директива #using](../preprocessor/hash-using-directive-cpp.md)
