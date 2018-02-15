---
title: "Компоновщик-ввод в файлах NETMODULE | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- MSIL linking
- linking [C++], modules
- .netmodules
- modules, Visual C++
ms.assetid: a4bcbe8a-4255-451d-853b-f88cfd82f4e1
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d1c30c56012dc14392ecdc6a089dcd88a217d6d8
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="netmodule-files-as-linker-input"></a>.NETMODULE-файлы в качестве входных файлов компоновщика
LINK.exe теперь принимает OBJ MSIL и netmodules-файлы в качестве входных данных. Выходной файл, создаваемый компоновщиком будет сборки или NETMODULE-файл во время выполнения независимо от любого из OBJ или NETMODULE, были введены в компоновщик.  
  
 netmodules-файлы, созданные компилятором Visual C++ с [/LN (Создание модуля MSIL)](../../build/reference/ln-create-msil-module.md) или компоновщиком с помощью [/NOASSEMBLY (Создание модуля MSIL)](../../build/reference/noassembly-create-a-msil-module.md). OBJ-файлов всегда создаются при компиляции Visual C++. Для других компиляторов Visual Studio используйте **/target: module** параметр компилятора.  
  
  Необходимо передать в компоновщик OBJ-файл из компиляции Visual C++, создавшей .netmodule. Передавая .netmodule больше не поддерживается, так как **/CLR: pure** и **/CLR: safe** параметры компилятора являются устаревшими в Visual Studio 2015 и будет удален в будущей версии компилятора.   
  
 Сведения о запуске компоновщика из командной строки см. в разделе [синтаксис командной строки компоновщика](../../build/reference/linker-command-line-syntax.md), [кода C/C++ на сборки в командной строке](../../build/building-on-the-command-line.md), и [набор переменных пути и среды для Построение из командной строки](../../build/setting-the-path-and-environment-variables-for-command-line-builds.md).  
  
 Передача NETMODULE-файл или DLL-файл для компоновщика был скомпилирован с компилятором Visual C++ с **/CLR** может привести к ошибке компоновщика. Дополнительные сведения см. в разделе [Выбор формата входных файлов .netmodule](../../build/reference/choosing-the-format-of-netmodule-input-files.md).  
  
 Компоновщик принимает машинные OBJ-файлы, а также MSIL OBJ-файлы, скомпилированные с **/CLR**. При передаче смешанных OBJ-файлов в ту же сборку, проверяемости выходного файла по умолчанию будет равно минимальному уровню проверяемости входных модулей. 
  
 Если в настоящее время у вас есть приложения, состоящего из двух или более сборок, и объединить в одну сборку, необходимо перекомпилировать сборку и затем связать OBJ-файлов или NETMODULE-файлов для создания в одну сборку.  
  
 Необходимо указать точку входа с помощью [/Entry (символ точки входа)](../../build/reference/entry-entry-point-symbol.md) при создании исполняемого образа.  
  
 При связывании с файлом OBJ- или .netmodule MSIL, используйте [/LTCG (Создание кода во время компоновки)](../../build/reference/ltcg-link-time-code-generation.md), в противном случае при обнаружении OBJ MSIL или NETMODULE-файл, он перезапустит компоновку с параметром/LTCG.  
  
 Файлы OBJ- или .netmodule MSIL также может быть передан cl.exe.  
  
 Входных файлов OBJ- или .netmodule MSIL не может иметь внедренных ресурсов. Ресурс внедрен в выходной файл (модуль или сборка) с [/ASSEMBLYRESOURCE (внедрение управляемого ресурса)](../../build/reference/assemblyresource-embed-a-managed-resource.md) компоновщика или с **/Resource** параметра компилятора в других компиляторов Visual Studio.  
  
 При выполнении компоновки MSIL, а также не указан [/LTCG (Создание кода во время компоновки)](../../build/reference/ltcg-link-time-code-generation.md), появится информационное сообщение, перезапуске компоновки. Это сообщение можно проигнорировать, но в целях повышения производительности компоновщика с компоновку MSIL следует явно задать **/LTCG**.  
  
## <a name="example"></a>Пример  
 В коде C++ блок catch конструкции try соответствующего будет вызываться для несистемного исключения. Тем не менее, по умолчанию среда CLR создает оболочку для несистемного исключения с <xref:System.Runtime.CompilerServices.RuntimeWrappedException>. При создании сборки из Visual C++, а модули не Visual C++ и требуется блок catch в коде C++, которые вызываются из соответствующей конструкции try при блока try создает исключение без системы, необходимо добавить  
  
 атрибут [assembly:System::Runtime::CompilerServices::RuntimeCompatibility(WrapNonExceptionThrows=false)] к исходному коду для модулей, отличных от C++.  
  
```  
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
 Можно изменить значение атрибута WrapNonExceptionThrows, изменить возможность перехвата исключения несистемного кода Visual C++.  
  
```  
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
 [Входные LINK-файлы](../../build/reference/link-input-files.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)