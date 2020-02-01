---
title: .netmodule файлы в качестве входных данных компоновщика
description: Описывает использование смешанных типов.obj перетаскивани.netmodule файлы в качестве входных данных компоновщика при создании сборок .NET.
ms.date: 01/30/2020
helpviewer_keywords:
- MSIL linking
- linking [C++], modules
- .netmodule files
- modules, Visual C++
ms.assetid: a4bcbe8a-4255-451d-853b-f88cfd82f4e1
no-loc:
- obj
- netmodule
- clr
- pure
- safe
ms.openlocfilehash: 83eab25624bdb81ba9191e4efe6a774551502ee0
ms.sourcegitcommit: c4528a7424d35039454f17778baf1b5f98fbbee7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/01/2020
ms.locfileid: "76912818"
---
# <a name="opno-locnetmodule-files-as-linker-input"></a>.netmodule файлы в качестве входных данных компоновщика

Link. exe принимает *`.obj`* MSIL и файлы *`.netmodule`* в качестве входных данных. Выходным файлом, созданным компоновщиком, является сборка или *`.netmodule`* файл без зависимости времени выполнения от любого из *`.obj`* или *`.netmodule`* файлов, которые были введены компоновщиком.

## <a name="remarks"></a>Заметки

*`.netmodule`* файлы создаются компилятором компилятором MSVC с параметром [/LN (создать модуль MSIL)](ln-create-msil-module.md) или компоновщиком с [/NOASSEMBLY (создание модуля MSIL)](noassembly-create-a-msil-module.md). файлы *`.obj`* всегда создаются при C++ компиляции. Для других компиляторов Visual Studio используйте параметр компилятора **/target:module**.

Компоновщику необходимо передать *`.obj`* файл из C++ компиляции, создавшей *`.netmodule`* . Передача *`.netmodule`* больше не поддерживается, так как **/clr:pure** и/clr **:safe** параметры компилятора являются устаревшими в Visual Studio 2015 и не поддерживаются в Visual Studio 2017 и более поздних версиях.

Сведения о том, как вызвать компоновщик из командной строки, см. в разделе [синтаксис командной строки компоновщика](linking.md), [используйте набор инструментов компилятором MSVC из командной строки](../building-on-the-command-line.md)и [Задайте путь и переменные среды для сборок из командной строки](../setting-the-path-and-environment-variables-for-command-line-builds.md).

Передача *`.netmodule`* или *`.dll`* файла компоновщику, который был скомпилирован компилятором компилятором msvc с помощью **/clr** может привести к ошибке компоновщика. Дополнительные сведения см. [в разделе Выбор форматаnetmodule входных файлов](choosing-the-format-of-netmodule-input-files.md).

Компоновщик принимает как собственные *`.obj`* файлы, так и файлы MSIL *`.obj`* , скомпилированные с помощью **/clr** . В одной сборке можно передавать файлы смешанного *`.obj`* . Проверка по умолчанию для результирующего выходного файла такая же, как и самая низкая проверяемая модуль ввода.

Можно изменить приложение, состоящее из двух или более сборок, которые должны содержаться в одной сборке. Перекомпилируйте источники сборок, а затем свяжите *`.obj`* файлы или файлы *`.netmodule`* , чтобы создать одну сборку.

Укажите точку входа, используя [/Entry (символ точки входа)](entry-entry-point-symbol.md) при создании исполняемого образа.

При связывании с файлом MSIL *`.obj`* или *`.netmodule`* используйте [/LTCG (создание кода во время компоновки)](ltcg-link-time-code-generation.md), в противном случае, если компоновщик встречает *`.obj`* или *`.netmodule`* MSIL, он перезапускает ссылку с параметром **/LTCG**. Вы увидите информационное сообщение о том, что ссылка перезапускается. Это сообщение можно проигнорировать, но для повышения производительности компоновщика явно укажите **/LTCG**.

Файлы MSIL *`.obj`* и *`.netmodule`* также могут передаваться в CL. exe.

Входные файлы MSIL *`.obj`* или *`.netmodule`* не могут иметь внедренные ресурсы. Внедрите ресурсы в выходной модуль или файл сборки с помощью параметра компоновщика [/ASSEMBLYRESOURCE (встраивание управляемого ресурса)](assemblyresource-embed-a-managed-resource.md) . Или используйте параметр компилятора **/Resource** в других компиляторах Visual Studio.

## <a name="examples"></a>Примеры

В C++ коде **`catch`** блок соответствующего **`try`** будет вызываться для исключения, не являющегося`System`. Однако по умолчанию среда CLR заключает исключения, не связанные с`System`, в <xref:System.Runtime.CompilerServices.RuntimeWrappedException>. Если сборка создается из C++ и другихC++ модулей и требуется, чтобы блок **`catch`** в C++ коде вызывался из соответствующего предложения **`try`** , когда блок **`try`** создает исключение, не связанное с`System`, необходимо добавить атрибут `[assembly:System::Runtime::CompilerServices::RuntimeCompatibility(WrapNonExceptionThrows=false)]` к исходному коду дляC++ модулей, не являющихся модулями.

```cpp
// MSIL_linking.cpp
// compile with: /c /clr
value struct V {};

ref struct MCPP {
   static void Test() {
      try {
         throw (gcnew V);
      }
      catch (V ^) {
         System::Console::WriteLine("caught non System exception in C++ source code file");
      }
   }
};

/*
int main() {
   MCPP::Test();
}
*/
```

Изменяя значение `Boolean` атрибута `WrapNonExceptionThrows`, можно изменить способность C++ кода перехватывать исключение, не являющееся`System`.

```csharp
// MSIL_linking_2.cs
// compile with: /target:module /addmodule:MSIL_linking.obj
// post-build command: link /LTCG MSIL_linking.obj MSIL_linking_2.netmodule /entry:MLinkTest.Main /out:MSIL_linking_2.exe /subsystem:console
using System.Runtime.CompilerServices;

// enable non System exceptions
[assembly:RuntimeCompatibility(WrapNonExceptionThrows=false)]

class MLinkTest {
   public static void Main() {
      try {
         MCPP.Test();
      }
      catch (RuntimeWrappedException) {
         System.Console.WriteLine("caught a wrapped exception in C#");
      }
   }
}
```

```Output
caught non System exception in C++ source code file
```

## <a name="see-also"></a>См. также:

- [Входные LINK-файлы](link-input-files.md)
- [Параметры компоновщика MSVC](linker-options.md)
