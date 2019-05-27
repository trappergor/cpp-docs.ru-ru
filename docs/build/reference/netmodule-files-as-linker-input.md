---
title: .NETMODULE-файлы в качестве входных файлов компоновщика
ms.date: 05/16/2019
helpviewer_keywords:
- MSIL linking
- linking [C++], modules
- .netmodules
- modules, Visual C++
ms.assetid: a4bcbe8a-4255-451d-853b-f88cfd82f4e1
ms.openlocfilehash: 50a0f0a1ff5f65a7512e8372de2fe5296c866dca
ms.sourcegitcommit: a10c9390413978d36b8096b684d5ed4cf1553bc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2019
ms.locfileid: "65837430"
---
# <a name="netmodule-files-as-linker-input"></a>.NETMODULE-файлы в качестве входных файлов компоновщика

Программа link.exe теперь принимает в качестве входных данных файлы MSIL OBJ и NETMODULE. Выходной файл, создаваемый компоновщиком, представляет собой сборку или NETMODULE-файл, который не зависит во время выполнения от входных файлов OBJ или NETMODULE компоновщика.

Файлы NETMODULE создаются компилятором MSVC с параметром [/LN (создать модуль MSIL)](ln-create-msil-module.md) или компоновщиком с параметром [/NOASSEMBLY (создать модуль MSIL)](noassembly-create-a-msil-module.md). Файлы OBJ всегда создаются при компиляции кода Visual C++. Для других компиляторов Visual Studio используйте параметр компилятора **/target:module**.

Компоновщику необходимо передать файл OBJ из компиляции Visual C++, в результате которой был создан файл NETMODULE. Передача файла NETMODULE больше не поддерживается, так как параметры компилятора **/clr:pure** и **/clr:safe** не рекомендуется использовать в Visual Studio 2015 и они не поддерживаются в Visual Studio 2017 и более поздних версий.

Сведения о вызове компоновщика из командной строки см. в статьях [Синтаксис командной строки компоновщика](linking.md), [Использование набора инструментов MSVC из командной строки](../building-on-the-command-line.md) и [Установка переменных пути и среды при сборке из командной строки](../setting-the-path-and-environment-variables-for-command-line-builds.md).

Передача в компоновщик файла NETMODULE или DLL, скомпилированного компилятором MSVC с параметром **/clr**, может привести к ошибке компоновщика. Дополнительные сведения см. в статье [Выбор формата входных файлов NETMODULE](choosing-the-format-of-netmodule-input-files.md).

Компоновщик принимает OBJ-файлы в машинном коде, а также OBJ-файлы MSIL, скомпилированные с параметром **/clr**. При передаче сочетания OBJ-файлов разных типов в одной сборке, проверяемость итогового выходного файла по умолчанию соответствует самому низкому уровню проверяемости входных модулей.

Если у вас есть приложение, состоящее из двух или нескольких сборок, но вы хотите, чтобы оно содержалось в одной сборке, необходимо перекомпилировать сборки, а затем скомпоновать файлы OBJ или NETMODULE, чтобы получить одну сборку.

При создании исполняемого образа нужно указать точку входа с помощью параметра [/ENTRY (символ точки входа)](entry-entry-point-symbol.md).

При компоновке с использованием файла MSIL OBJ или NETMODULE укажите параметр [/LTCG (создание кода во время компоновки)](ltcg-link-time-code-generation.md). В противном случае, когда компоновщику встретится файл MSIL OBJ или NETMODULE, компоновка перезапустится с параметром /LTCG.

OBJ- или NETMODULE-файлы MSIL также можно передавать в cl.exe.

Входные OBJ- или NETMODULE-файлы MSIL не могут иметь внедренных ресурсов. Ресурс внедряется в выходной файл (модуль или сборку) с помощью параметра компоновщика [/ASSEMBLYRESOURCE (внедрить управляемый ресурс)](assemblyresource-embed-a-managed-resource.md) или параметра компилятора **/resource** в других компиляторах Visual Studio.

Если при выполнении компоновки MSIL не указать параметр [/LTCG (создание кода во время компоновки)](ltcg-link-time-code-generation.md), появится информационное сообщение о том, что компоновка перезапускается. Это сообщение можно проигнорировать, но, чтобы повысить производительность компоновки MSIL, укажите параметр **/LTCG** явным образом.

## <a name="example"></a>Пример

В коде C++ в случае несистемного исключения будет вызван блок **catch** соответствующего блока **try**. Однако по умолчанию среда CLR заключает несистемные исключения в <xref:System.Runtime.CompilerServices.RuntimeWrappedException>. Когда сборка создается на основе как модулей Visual C++, так и модулей не на Visual C++ и требуется, чтобы блок **catch** в коде C++ вызывался из соответствующего предложения **try**, когда в блоке **try** происходит несистемное исключение, необходимо добавить атрибут `[assembly:System::Runtime::CompilerServices::RuntimeCompatibility(WrapNonExceptionThrows=false)]` в исходный код модулей не на C++.

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

## <a name="example"></a>Пример

Изменяя логическое значение атрибута `WrapNonExceptionThrows`, вы контролируете возможность перехвата несистемного исключения в коде Visual C++.

```cpp
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

## <a name="see-also"></a>См. также

- [Входные LINK-файлы](link-input-files.md)
- [Параметры компоновщика MSVC](linker-options.md)
