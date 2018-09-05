---
title: -clr (компиляция CLR) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /CLR
- VC.Project.VCNMakeTool.CompileAsManaged
- VC.Project.VCCLCompilerTool.CompileAsManaged
dev_langs:
- C++
helpviewer_keywords:
- cl.exe compiler, common language runtime option
- -clr compiler option [C++]
- clr compiler option [C++]
- /clr compiler option [C++]
- Managed Extensions for C++, compiling
- common language runtime, /clr compiler option
ms.assetid: fec5a8c0-40ec-484c-a213-8dec918c1d6c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ff46958afea8825f29941d9f3cbead20c533c76c
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43676989"
---
# <a name="clr-common-language-runtime-compilation"></a>/clr (компиляция CLR)
Позволяет приложениям и компонентам использовать возможности из среды CLR.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/clr[:options]  
```  
  
## <a name="arguments"></a>Аргументы  
 `options`  
 Один или несколько из следующих параметров, разделенных запятыми.  
  
 **/clr**  
 Создает метаданные для приложения. Создает метаданные для приложения, которые могут использовать другие CLR-приложения, а также позволяет приложению применять типы и данные в метаданных других CLR-компонентов.  
  
 Дополнительные сведения см. в разделе .  
  
 [Смешанные (собственные и управляемые) сборки](../../dotnet/mixed-native-and-managed-assemblies.md) и  
  
 [Практическое: Миграция в/CLR](../../dotnet/how-to-migrate-to-clr.md).  
  
 **/clr:pure**  
 /clr:pure не рекомендуется к использованию. Будущие версии компилятора могут не поддерживать этот параметр. Мы рекомендуем перенести код, который должен быть чистым кодом MSIL, на C#.  
  
 **/clr:safe**  
 /clr:safe не рекомендуется к использованию. Будущие версии компилятора могут не поддерживать этот параметр. Мы рекомендуем перенести код, который должен быть чистого MSIL для C#. 
  
 **/clr:noAssembly**  
 Указывает, что манифест сборки не должен быть включен в выходной файл. По умолчанию параметр **noAssembly** отключен.  
  
 Параметр **NoAssembly** не рекомендуется. Взамен рекомендуется использовать [/LN (Create MSIL Module)](../../build/reference/ln-create-msil-module.md) .  
  
 Управляемая программа, которая не содержит метаданных сборки в манифесте, называется *модулем*. Параметр **noAssembly** можно использовать только для создания модуля. Если компиляция выполняется с параметром [/c](../../build/reference/c-compile-without-linking.md) и **/clr:noAssembly**, укажите параметр [/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md) на фазе компоновщика, чтобы создать модуль.  
  
 До выпуска Visual C++ 2005 параметр **/clr:noAssembly** требовал указания **/LD**. Теперь параметр **/LD** подразумевается при указании **/clr:noAssembly**.  
  
 **/clr:initialAppDomain**  
 Позволяет приложению Visual C++ для запуска в версии 1 среды CLR.  Приложения, скомпилированные с использованием **initialAppDomain** , не должны использоваться приложением, которое применяет ASP.NET, так как этот компонент не поддерживается в версии 1 среды CLR.  
  
 **/clr:nostdlib**  
 Указывает компилятору игнорировать каталог \clr по умолчанию. Компилятор выдает ошибки при включении нескольких версий библиотеки DLL, например System.dll. При использовании этого параметра вы можете указать конкретную платформу для компиляции.  
  
## <a name="remarks"></a>Примечания  
 Управляемый код — это код, который среда CLR может проверять и контролировать. Управляемый код может обращаться к управляемым объектам. Для получения дополнительной информации см. [/clr Restrictions](../../build/reference/clr-restrictions.md).  
  
 Сведения о разработке приложений, которые определяют и используют управляемые типы, см. в разделе [Component Extensions for Runtime Platforms](../../windows/component-extensions-for-runtime-platforms.md).  
  
 Приложение, скомпилированное с использованием **/clr** , может содержать или не содержать управляемые данные.  
  
 Чтобы включить отладку для управляемых приложений, см. в разделе [/ASSEMBLYDEBUG (Добавление атрибута DebuggableAttribute)](../../build/reference/assemblydebug-add-debuggableattribute.md).  
  
 В куче сбора мусора будут созданы экземпляры только типов среды CLR. Дополнительные сведения см. в разделе [классы и структуры](../../windows/classes-and-structs-cpp-component-extensions.md). Для компиляции функции в машинный код используйте директиву `unmanaged` pragma. Дополнительные сведения см. в разделе [управляемые, неуправляемые](../../preprocessor/managed-unmanaged.md).  
  
 По умолчанию параметр **/clr** отключен. Если **/clr** включен, также действует и параметр **/MD** . Дополнительные сведения см. в разделе [/MD, /MT, /LD (использование библиотеки времени выполнения)](../../build/reference/md-mt-ld-use-run-time-library.md). Параметр **/MD** гарантирует, что из файлов стандартных заголовков (H-файлов) выбираются динамически связанные, многопотоковые версии процедур среды выполнения. Многопоточность необходима для управляемого программирования, так как сборщик мусора CLR запускает методы завершения во вспомогательном потоке.  
  
 Если компиляция выполняется с помощью **/c**, можно указать тип среды CLR выходного файла, задав [/CLRIMAGETYPE](../../build/reference/clrimagetype-specify-type-of-clr-image.md).  
  
 **/clr** подразумевает указание **/EHa**, и никакие другие параметры **/EH** не поддерживаются для **/clr**. Дополнительные сведения см. в статье [/EH (модель обработки исключений)](../../build/reference/eh-exception-handling-model.md).  
  
 Сведения о том, как определить тип образа среды файла CLR, см. в разделе [/CLRHEADER](../../build/reference/clrheader.md).  
  
 Все модули, передаваемые компоновщику при определенном вызове, должны компилироваться с одним и тем же параметром компилятора, указывающим библиотеку времени выполнения (**/MD** или **/LD**).  
  
 Используйте параметр компоновщика [/ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md) для внедрения ресурса в сборку. Параметры компоновщика[/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md), [/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)и [/KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md) также позволяют настраивать способ создания сборки.  
  
 При использовании **/clr** символ `_MANAGED` определяется как 1. Для получения дополнительной информации см. [Predefined Macros](../../preprocessor/predefined-macros.md).  
  
 Глобальные переменные в файлах собственных объектов инициализируются первыми (во время выполнения DllMain, если исполняемый файл — библиотека DLL), а затем инициализируются глобальные переменные управляемого раздела (перед выполнением любого управляемого кода). `#pragma`[init_seg](../../preprocessor/init-seg.md) влияет только на порядок инициализации в управляемых и неуправляемых категориях.  
  
## <a name="metadata-and-unnamed-classes"></a>Метаданные и неименованные классы  
 Неименованные классы отображаются в метаданных следующим образом: `$UnnamedClass$`*crc-текущего-файла*`$`*индекс*`$`, где *индекс* — это номер неименованного класса в компиляции. Например, следующий код создает неименованный класс в метаданных.  
  
```  
// clr_unnamed_class.cpp  
// compile by using: /clr /LD  
class {} x;  
```  
  
 Для просмотра метаданных используйте ildasm.exe.  
  
## <a name="managed-extensions-for-c"></a>Управляемые расширения для C++  
 Visual C++ больше не поддерживает параметр **/clr:oldsyntax** . Этот параметр перестал поддерживаться в Visual Studio 2005. Поддерживаемый синтаксис для написания управляемого кода на C++ — C++/CLI. Для получения дополнительной информации см. [Component Extensions for Runtime Platforms](../../windows/component-extensions-for-runtime-platforms.md).  
  
 Если у вас есть код, использующий управляемые расширения для C++, мы рекомендуем портировать его с использованием синтаксиса C++/CLI. Сведения о том, как перенести код, см. в разделе [C++/CLI Migration Primer](../../dotnet/cpp-cli-migration-primer.md).  
  
#### <a name="to-set-this-compiler-option-in-visual-studio"></a>Установка параметра компилятора в Visual Studio  
  
1.  В области **Обозреватель решений**щелкните правой кнопкой мыши имя проекта и выберите пункт **Свойства** , чтобы открыть диалоговое окно **Страницы свойств** .  
  
2.  Выберите папку **Свойства конфигурации** .  
  
3.  На странице свойств **Общие** измените свойство **Поддержка общеязыковой среды выполнения (CLR)** .  
  
    > [!NOTE]
    >  Если параметр **/clr** включен в диалоговом окне **Страницы свойств** , будут также изменены свойства параметров компилятора, несовместимые с **/clr** . Например, если задан параметр **/RTC** и затем включен **/clr** , параметр **/RTC** будет отключен.  
    >   
    >  Кроме того, при отладке приложения **/clr** следует установить для свойства **Тип отладчика** значение **Смешанный** или **Только управляемый код**. Дополнительные сведения см. в разделе [параметры проекта для конфигурации отладки C++](/visualstudio/debugger/project-settings-for-a-cpp-debug-configuration).  
  
     Сведения о том, как создать модуль, см. в разделе [/NOASSEMBLY (Создание модуля MSIL)](../../build/reference/noassembly-create-a-msil-module.md).  
  
#### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CompileAsManaged%2A>.  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)