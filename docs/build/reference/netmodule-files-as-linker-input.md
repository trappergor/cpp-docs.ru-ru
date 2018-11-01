---
title: .NETMODULE-файлы в качестве входных файлов компоновщика
ms.date: 11/04/2016
helpviewer_keywords:
- MSIL linking
- linking [C++], modules
- .netmodules
- modules, Visual C++
ms.assetid: a4bcbe8a-4255-451d-853b-f88cfd82f4e1
ms.openlocfilehash: 050736e5536a1e38b73524f31491b3a01dc99193
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50443581"
---
# <a name="netmodule-files-as-linker-input"></a>.NETMODULE-файлы в качестве входных файлов компоновщика

LINK.exe теперь принимает OBJ MSIL и netmodules-файлы в качестве входных данных. Выходной файл, создаваемый компоновщиком является сборки или NETMODULE-файл с не зависят от времени выполнения на любом из OBJ или NETMODULE, были введены в компоновщик.

netmodules-файлы создаются с помощью компилятора Visual C++ с [/LN (Создание модуля MSIL)](../../build/reference/ln-create-msil-module.md) или компоновщиком с помощью [/NOASSEMBLY (Создание модуля MSIL)](../../build/reference/noassembly-create-a-msil-module.md). OBJ-файлов всегда создаются при компиляции Visual C++. Для других компиляторов Visual Studio используйте **/target: module** параметр компилятора.

Необходимо передать в компоновщик OBJ-файл из компиляции Visual C++, который создан .netmodule. Передавая .netmodule больше не поддерживается, так как **/CLR: pure** и **/CLR: safe** параметры компилятора признаны устаревшими в Visual Studio 2015 и не поддерживается в Visual Studio 2017.

Сведения о том, как вызывать компоновщика из командной строки, см. в разделе [синтаксис командной строки компоновщика](../../build/reference/linker-command-line-syntax.md), [кода C/C++ на сборки в командной строке](../../build/building-on-the-command-line.md), и [задайте путь и переменные среды для Сборки из командной строки](../../build/setting-the-path-and-environment-variables-for-command-line-builds.md).

Путем передачи NETMODULE-файл или DLL-файла компоновщика, скомпилированного с помощью компилятора Visual C++ с **/CLR** может привести к ошибке компоновщика. Дополнительные сведения см. в разделе [Выбор формата входных файлов .netmodule](../../build/reference/choosing-the-format-of-netmodule-input-files.md).

Компоновщик принимает машинные OBJ-файлы, а также MSIL OBJ-файлы, скомпилированные с использованием **/CLR**. При передаче смешанных OBJ-файлов в той же сборки, проверяемость выходного файла по умолчанию будет равен самый низкий уровень проверяемости входных модулей.

Если вы уже создали приложение, которое состоит из двух или нескольких сборок и приложение должен содержаться в одной сборке, необходимо перекомпилировать сборку и затем связать OBJ-файлов или netmodules-файлы, чтобы получить единую сборку.

Необходимо указать учетную запись точки с помощью [/Entry (символ точки входа)](../../build/reference/entry-entry-point-symbol.md) при создании исполняемого образа.

При связывании с помощью файла OBJ- или .netmodule MSIL, использовать [/LTCG (Создание кода во время компоновки)](../../build/reference/ltcg-link-time-code-generation.md), в противном случае при обнаружении MSIL .obj или NETMODULE-файл, оно будет перезапущено ссылку с параметром/LTCG.

Файлы OBJ- или .netmodule MSIL также могут передаваться в cl.exe.

Входные файлы OBJ- или .netmodule MSIL не может иметь внедренные ресурсы. Ресурс внедрен в выходной файл (модуля или сборки) с [/ASSEMBLYRESOURCE (внедрение управляемого ресурса)](../../build/reference/assemblyresource-embed-a-managed-resource.md) параметр компоновщика или с **/Resource** параметр компилятора в другие компиляторы Visual Studio.

При выполнении компоновки MSIL, и в том случае, если вы не указано [/LTCG (Создание кода во время компоновки)](../../build/reference/ltcg-link-time-code-generation.md), появится информационное сообщение, перезапуске компоновки. Это сообщение можно проигнорировать, но в целях повышения производительности компоновщика с MSIL-связывание, явно укажите **/LTCG**.

## <a name="example"></a>Пример

В коде C++ **catch** блок соответствующего **попробуйте** будет вызываться для несистемного исключения. Тем не менее, по умолчанию среда CLR создает оболочку для несистемных исключений с помощью <xref:System.Runtime.CompilerServices.RuntimeWrappedException>. При создании сборки из модулей Visual C++ и не - Visual C++ и хотите **catch** блока в C++ код должен быть вызван из соответствующего **попробуйте** предложение при **попробуйте**блок вызывает исключение без системы, необходимо добавить `[assembly:System::Runtime::CompilerServices::RuntimeCompatibility(WrapNonExceptionThrows=false)]` атрибут к исходному коду для модулей не C++.

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

Изменив логическое значение `WrapNonExceptionThrows` атрибут, изменить возможность перехвата исключения несистемных кода Visual C++.

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

- [Входные LINK-файлы](../../build/reference/link-input-files.md)
- [Параметры компоновщика](../../build/reference/linker-options.md)
