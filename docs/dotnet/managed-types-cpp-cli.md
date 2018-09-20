---
title: Управляемые типы (C + +/ CLI) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: ae7abc7d8683d282be4c2e1cd24d8f51bd28be86
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46437786"
---
# <a name="managed-types-ccli"></a>Управляемые типы (C++/CLI)

Visual C++ предоставляет доступ к функциям .NET с помощью управляемых типов, которые предоставляют поддержку для функций среды CLR и их использование регулируется преимущества и ограничения среды выполнения.

## <a name="main_functions"></a> Управляемые типы и функция main

При написании приложения с помощью **/CLR**, аргументы **main()** функция не может быть управляемого типа.

Ниже приведен пример правильной подписи.

```cpp
// managed_types_and_main.cpp
// compile with: /clr
int main(int, char*[], char*[]) {}
```

## <a name="dotnet"></a> Эквиваленты собственным типам C++ в .NET framework

В следующей таблице показаны ключевые слова для встроенных типов Visual C++, которые являются псевдонимами предопределенных типов в **системы** пространства имен.

|Тип Visual C++|Тип платформы .NET Framework|
|-----------------------|-------------------------|
|**bool**|**System.Boolean**|
|**автоматический char** (см. в разделе [/j](../build/reference/j-default-char-type-is-unsigned.md) Дополнительные сведения)|**System.SByte**|
|**unsigned char**|**System.Byte**|
|**wchar_t**|**System.Char**|
|**двойные** и **long double**|**System.Double**|
|**float**|**System.Single**|
|**int**, **целочисленное число со знаком**, **long**, и **автоматический долго**|**System.Int32**|
|**unsigned int** и **unsigned long**|**System.UInt32**|
|**__int64** и **автоматический __int64**|**System.Int64**|
|**unsigned __int64**|**System.UInt64**|
|**короткий** и **автоматический short**|**System.Int16**|
|**unsigned short**|**System.UInt16**|
|**void**|**System.Void**|

## <a name="version_issues"></a> Проблемы версий, связанные с типами значений, вложенными в собственные типы

Рассмотрим компонент сборки со знаком (строгое имя), используемый для построения клиентской сборки. Компонент содержит тип значения, который используется в клиенте в качестве типа члена собственного объединения, классом или массивом. При изменении размера и типа значения, будущие версии компонента клиента должны быть перекомпилированы.

Создание файла ключа с [sn.exe](/dotnet/framework/tools/sn-exe-strong-name-tool) (`sn -k mykey.snk`).

### <a name="example"></a>Пример

Следующий пример — это компонент.

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

Этот образец является клиентом:

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

### <a name="output"></a>Вывод

```Output
S.i = 5
S.i = 6
S.i = 10
S.i = 11
```

### <a name="comments"></a>Комментарии

Тем не менее если добавить другой элемент `struct S` в nested_value_types.cpp, (например, `double d;`) и скомпилировать компонент заново без перекомпиляции клиента, в результате необработанного исключения (типа <xref:System.IO.FileLoadException?displayProperty=fullName>).

## <a name="test_equality"></a> Практическое: проверка на равенство

В следующем примере проверка на равенство, использующий управляемые расширения для C++ основана на которые указывают дескрипторы.

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

IL-код для этой программы показано, что возвращаемое значение реализуется с помощью вызова функции op_Equality.

```MSIL
IL_0012:  call       bool [mscorlib]System.String::op_Equality(string,
                                                               string)
```

## <a name="diagnose_fix"></a> Практическое: диагностика и устранение проблем совместимости сборок

В этом разделе объясняется, что может произойти, если версия сборки, которая использовалась во время компиляции не соответствует версии сборки, указанной во время выполнения и способы устранения проблемы.

При компиляции сборки, она может ссылаться на другие сборки с `#using` синтаксис. Во время компиляции эти сборки осуществляется с помощью компилятора. Сведения из этих сборок используется для принятия решений по оптимизации.

Тем не менее, если изменены и перекомпилированы указанной ссылками сборки и ссылочную сборку, зависящий от он этого не сделать, то сборки могут не быть совместимы. Решения по оптимизации, которые были верными сначала могут быть неправильными по отношению к новой версии сборки. Из-за этих несовместимостей, могут возникнуть различные ошибки среды выполнения. Нет определенного исключения, будут получены в таких случаях. Способ, регистрируются во время выполнения, зависит от характера изменения кода, который вызвал проблему.

Эти ошибки не должно быть проблемой в окончательный рабочий код, до тех пор, пока все приложение перестраивается в окончательной версии продукта. Сборки, которые выпускаются к общедоступному должны быть помечены официальный номер версии, это даст гарантию, что эти проблемы удастся избежать. Дополнительные сведения см. в разделе [Версии сборок](/dotnet/framework/app-domains/assembly-versioning).

### <a name="diagnosing-and-fixing-an-incompatibility-error"></a>Диагностика и устранение ошибок несовместимости

1. Если исключение времени выполнения или другие условия ошибки, возникающие в коде, который ссылается на другую сборку и иметь причину, может понадобиться работать с устаревшими сборки.

1. Во-первых изолировать и воспроизвести исключение или иную ошибку. Проблема, возникающая из-за устаревших исключения должна быть воспроизводимой.

1. Проверьте отметки времени всех сборок, на которые ссылается приложение.

1. Если отметки времени любые связанные сборки более поздней версии, чем отметка времени последней компиляции приложения, приложения является устаревшим. В этом случае выполните повторную компиляцию приложения с самой последней сборки и внесите необходимые изменения кода.

1. Снова запустить приложение, выполните действия, которые воспроизводят проблему и убедитесь, что исключение не возникает.

### <a name="example"></a>Пример

Следующая программа иллюстрирует эту проблему путем снижения уровня доступности метода и пытается получить доступ к этому методу в другую сборку без повторной компиляции. Попробуйте компилировать `changeaccess.cpp` первого. Это связанная сборка, которая приведет к изменению. Затем скомпилируйте `referencing.cpp`. Компиляция завершается успешно. Теперь уменьшите доступность вызванного метода. Перекомпилируйте `changeaccess.cpp` с флагом `/DCHANGE_ACCESS`. Это делает метод защищенным, а не закрытым, поэтому больше может вызываться по закону. Без повторной компиляции `referencing.exe`, снова запустить приложение. Исключение <xref:System.MethodAccessException> приведет к.

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

## <a name="see-also"></a>См. также

[Программирование .NET с использованием C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)

[Совместимость с другими языками .NET (C++/CLI)](../dotnet/interoperability-with-other-dotnet-languages-cpp-cli.md)

[Управляемые типы (C++/CLI)](../dotnet/managed-types-cpp-cli.md)

[Директива #using](../preprocessor/hash-using-directive-cpp.md)
