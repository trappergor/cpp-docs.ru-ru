---
title: Стандартные макросы для команд и свойств сборки
ms.date: 05/29/2018
f1_keywords:
- VC.Project.VCCLCompilerTool.GenerateXMLDocumentationFiles
- VC.Project.VCCLCompilerTool.XMLDocumentationFileName
helpviewer_keywords:
- $(FrameworkSDKDir) macro
- ProjectName macro $(ProjectName)
- DevEnvDir macro $(DevEnvDir)
- $(DevEnvDir) macro
- TargetPath macro $(TargetPath)
- VSInstallDir macro $(VSInstallDir)
- $(InputFileName) macro
- $(SolutionFileName) macro
- macros [C++], build macros
- InputFileName macro $(InputFileName)
- $(VCInstallDir) macro
- $(IntDir) macro
- $(ConfigurationName) macro
- SolutionDir macro $(SolutionDir)
- $(TargetPath) macro
- $(Inherit) macro
- $(SolutionPath) macro
- WebDeployRoot macro $(WebDeployRoot)
- WebDeployPath macro $(WebDeployPath)
- StopEvaluating macro $(StopEvaluating)
- $(RootNamespace) macro
- $(WebDeployRoot) macro
- ProjectPath macro $(ProjectPath)
- $(ProjectPath) macro
- $(InputDir) macro
- SolutionName macro $(SolutionName)
- ProjectExt macro $(ProjectExt)
- $(TargetExt) macro
- $(ProjectFileName) macro
- TargetName macro $(TargetName)
- $(References) macro
- References macro $(References)
- TargetExt macro $(TargetExt)
- ProjectDir macro $(ProjectDir)
- $(TargetDir) macro
- SolutionExt macro $(SolutionExt)
- $(SolutionDir) macro
- ProjectFileName macro $(ProjectFileName)
- VCInstallDir macro $(VCInstallDir)
- $(InputExt) macro
- $(TargetFileName) macro
- $(SolutionExt) macro
- PlatformName macro $(PlatformName)
- IntDir macro $(IntDir)
- $(FrameworkVersion) macro
- $(ProjectDir) macro
- build macros [C++]
- InputPath macro $(InputPath)
- $(VSInstallDir) macro
- $(WebDeployPath) macro
- TargetFileName macro $(TargetFileName)
- NoInherit macro $(NoInherit)
- ConfigurationName macro $(ConfigurationName)
- $(ProjectExt) macro
- TargetDir macro $(TargetDir)
- InputName macro $(InputName)
- $(ProjectName) macro
- FrameworkSDKDir macro $(FrameworkSDKDir)
- $(ParentName) macro
- InputExt macro $(InputExt)
- $(SafeRootNamespace) macro
- InputDir macro $(InputDir)
- $(FxCopDir) macro
- $(RemoteMachine) macro
- Inherit macro $(Inherit)
- FrameworkVersion macro $(FrameworkVersion)
- $(StopEvaluating) macro
- $(OutDir) macro
- FrameworkDir macro $(FrameworkDir)
- SolutionFileName macro $(SolutionFileName)
- $(NoInherit) macro
- RemoteMachine macro $(RemoteMachine)
- properties [C++], build property macros
- $(TargetName) macro
- $(SolutionName) macro
- $(InputPath) macro
- ParentName macro $(ParentName)
- OutDir macro $(OutDir)
- SafeRootNamespace macro $(SafeRootNamespace)
- FxCopDir macro $(FxCopDir)
- $(InputName) macro
- RootNamespace macro $(RootNamespace)
- builds [C++], macros
- $(FrameworkDir) macro
- $(PlatformName) macro
- SolutionPath macro $(SolutionPath)
ms.assetid: 239bd708-2ea9-4687-b264-043f1febf98b
ms.openlocfilehash: 669114691bc89c1e8136e07a949be57cda3d71b9
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57826646"
---
# <a name="common-macros-for-build-commands-and-properties"></a>Стандартные макросы для команд и свойств сборки

В зависимости от параметров установки Visual Studio может предоставлять вам сотни макросов. Они соответствуют свойствам MSBuild, заданным по умолчанию, указанным в файлах PROPS или TARGETS либо в параметрах проекта. Эти макросы можно использовать в любом месте диалогового окна **Страницы свойств** проекта, где допустимы строки. В этих макросах регистр не учитывается.

## <a name="view-the-current-properties-and-macros"></a>Просмотр текущих свойств и макросов

Для просмотра доступных макросов на любой странице свойств в диалоговом окне **Страницы свойств** нажмите на стрелку раскрывающегося списка в конце строки свойств. Если доступен пункт **Изменить**, щелкните его и в диалоговом окне редактирования выберите **Макросы**. Текущий набор свойств и макросов, видимых для Visual Studio, отображается вместе с текущим значением для каждого. Дополнительные сведения см. в разделе **specifying User-Defined значения** раздел [Справочник по страницам свойств проекта C++](property-pages-visual-cpp.md).

## <a name="list-of-common-macros"></a>Список общих макросов

В таблице описано несколько распространенных доступных макросов. Это далеко не полный список. Дополнительные сведения о том, как определения свойств MSBuild создаются и используются как макросы в файлах VCXPROJ, PROPS и TARGETS, см. в разделе [Свойства MSBuild](/visualstudio/msbuild/msbuild-properties).

|Макрос|Описание:|
|-----------|-----------------|
|**$(Configuration)**|Имя текущей конфигурации проекта, например "Debug".|
|**$(DevEnvDir)**|Папка установки Visual Studio (определяется как диск + путь); включает обратную косую черту "\\".|
|**$(FrameworkDir)**|Каталог, в котором установлена платформа .NET Framework.|
|**$(FrameworkSDKDir)**|Каталог, в котором установлена платформа .NET Framework. Платформу .NET Framework можно установить в составе Visual Studio или отдельно.|
|**$(FrameworkVersion)**|Версия платформы .NET Framework, используемая Visual Studio. В сочетании с **$(FrameworkDir)**— полный путь к версии .NET Framework, используемой Visual Studio.|
|**$(FxCopDir)**|Путь к файлу fxcop.cmd. Файл fxcop.cmd устанавливается не со всеми выпусками Visual C++.|
|**$(IntDir)**|Путь к каталогу, заданному для промежуточных файлов. Если это относительный путь, промежуточные файлы передаются по этому пути, добавленному к каталогу проекта. Этот путь должен содержать косую черту в конце. Путь разрешается в значение для свойства **Intermediate Directory** . Не используйте **$(OutDir)** для определения этого свойства.|
|**$(OutDir)**|Путь к каталогу выходных файлов. Если это относительный путь, выходные файлы передаются по этому пути, добавленному к каталогу проекта. Этот путь должен содержать косую черту в конце. Путь разрешается в значение для свойства **Output Directory** . Не используйте **$(IntDir)** для определения этого свойства.|
|**$(Platform)**|Имя текущей платформы проекта, например Win32.|
|**$(ProjectDir)**|Каталог проекта (определяется как диск + путь); включает обратную косую черту "\\".|
|**$(ProjectExt)**|Расширение файла проекта. Включает символ "." перед расширением файла.|
|**$(ProjectFileName)**|Имя файла проекта (определяется как базовое имя + расширение файла).|
|**$(ProjectName)**|Базовое имя проекта.|
|**$(ProjectPath)**|Абсолютный путь к проекту (определяется как диск + путь + базовое имя + расширение файла).|
|**$(RemoteMachine)**|Задайте значение свойства **Remote Machine** на странице свойств отладки. Дополнительные сведения см. в разделе [Изменение параметров проекта для конфигурации отладки C или C++](/visualstudio/debugger/project-settings-for-a-cpp-debug-configuration) .|
|**$(RootNameSpace)**|Пространство имен (при наличии), содержащее приложение.|
|**$(SolutionDir)**|Каталог решения (определяется как диск + путь); включает обратную косую черту "\\". Он определяется только при сборке решения в интегрированной среде разработки.|
|**$(SolutionExt)**|Расширение файла решения. Включает символ "." перед расширением файла. Он определяется только при сборке решения в интегрированной среде разработки.|
|**$(SolutionFileName)**|Имя файла решения (определяется как базовое имя + расширение файла). Он определяется только при сборке решения в интегрированной среде разработки.|
|**$(SolutionName)**|Базовое имя решения. Он определяется только при сборке решения в интегрированной среде разработки.|
|**$(SolutionPath)**|Абсолютный путь к решению (определяется как диск + путь + базовое имя + расширение файла). Он определяется только при сборке решения в интегрированной среде разработки.|
|**$(TargetDir)**|Каталог основного выходного файла для сборки (определяется как диск + путь); включает обратную косую черту "\\".|
|**$(TargetExt)**|Расширение имени основного выходного файла сборки. Включает символ "." перед расширением файла.|
|**$(TargetFileName)**|Имя основного выходного файла для сборки (определяется как базовое имя + расширение файла).|
|**$(TargetName)**|Базовое имя основного выходного файла сборки.|
|**$(TargetPath)**|Абсолютный путь к основному выходному файлу для сборки (определяется как диск + путь + базовое имя + расширение файла).|
|**$(VCInstallDir)**|Каталог с содержимым C++ из установки Visual Studio. Это свойство содержит версию целевого набора инструментов Visual C++, которая может отличаться от основного приложения Visual Studio. Например, при сборке с помощью `$(PlatformToolset) = v140` макрос **$(VCInstallDir)** содержит путь к установке Visual C++ 2015.|
|**$(VSInstallDir)**|Каталог, в котором установлено программное обеспечение Visual Studio. Это свойство содержит версию целевого набора инструментов Visual Studio, которая может отличаться от основного приложения Visual Studio. Например, при построении с помощью `$(PlatformToolset) = v110`свойство **$(VSInstallDir)** содержит путь к установке Visual Studio 2012.|
|**$(WebDeployPath)**|Относительный путь от корня веб-развертывания до каталога выходных данных проекта. Возвращает значение такого же типа, что и аргумент <xref:Microsoft.VisualStudio.VCProjectEngine.VCWebDeploymentTool.RelativePath%2A>.|
|**$(WebDeployRoot)**|Абсолютный путь к расположению **\<localhost>**. Например, c:\inetpub\wwwroot.|

## <a name="obsolete-macros"></a>Устаревшие макросы

Система сборки для C++ значительно изменилась между выходом версий Visual Studio 2008 и Visual Studio 2010. Многие макросы, используемые в более ранних типах проектов, были заменены новыми. Эти макросы больше не используются или были заменены эквивалентными свойствами или значениями [макроса метаданных элемента](/visualstudio/msbuild/itemmetadata-element-msbuild) (**%(**_name_**)**). Макросы, помеченные как "перенесенные", можно обновить с помощью средства миграции проекта. Если проект, содержащий макрос, переносится из Visual Studio 2008 или более ранней версии в Visual Studio 2010, Visual Studio преобразует макрос в эквивалентный текущий макрос. Более поздние версии Visual Studio не могут преобразовывать проекты с Visual Studio 2008 и более ранних версий в новые типы проектов. Необходимо преобразовать эти проекты в два этапа — сначала преобразуйте их в Visual Studio 2010, а затем преобразуйте результат для более новой версии Visual Studio. Дополнительные сведения см. в статье [Общие сведения о возможных проблемах, возникающих при обновлении](../../porting/overview-of-potential-upgrade-issues-visual-cpp.md).

|Макрос|Описание:|
|-----------|-----------------|
|**$(InputDir)**|(Перенесен.) Каталог входного файла (определяется как диск + путь); включает обратную косую черту "\\". Если проект является входными данными, этот макрос эквивалентен **$(ProjectDir)**.|
|**$(InputExt)**|(Перенесен.) Расширение имени входного файла. Включает символ "." перед расширением файла. Если проект является входными данными, этот макрос эквивалентен **$(ProjectExt)**. Для исходных файлов это **%(Extension)**.|
|**$(InputFileName)**|(Перенесен.) Имя входного файла (определяется как базовое имя + расширение файла). Если проект является входными данными, этот макрос эквивалентен **$(ProjectFileName)**. Для исходных файлов это **%(Identity)**.|
|**$(InputName)**|(Перенесен.) Базовое имя входного файла. Если проект является входными данными, этот макрос эквивалентен **$(ProjectName)**. Для исходных файлов это **%(Filename)**.|
|**$(InputPath)**|(Перенесен.) Абсолютный путь к входному файлу (определяется как диск + путь + базовое имя + расширение файла). Если проект является входными данными, этот макрос эквивалентен **$(ProjectPath)**. Для исходных файлов это **%(FullPath)**.|
|**$(ParentName)**|Имя элемента, содержащего данный элемент проекта. Это будет имя родительской папки или имя проекта.|
|**$(SafeInputName)**|Имя файла как допустимое имя класса (без расширения файла). Это свойство не имеет точного эквивалента.|
|**$(SafeParentName)**|Имя непосредственного родителя в допустимом формате. Например, форма является родителем RESX-файла. Это свойство не имеет точного эквивалента.|
|**$(SafeRootNamespace)**|Имя пространства имен, в которое мастера проекта будут добавлять код. Это пространство имен будет содержать только те символы, которые разрешены в допустимых идентификаторах C++. Это свойство не имеет точного эквивалента.|

## <a name="see-also"></a>См. также

- [Проекты Visual Studio — C++](../creating-and-managing-visual-cpp-projects.md)
- [Руководство по переносу и обновлению Visual C++](../../porting/visual-cpp-porting-and-upgrading-guide.md)
- [Общие сведения о возможных проблемах, возникающих при обновлении](../../porting/overview-of-potential-upgrade-issues-visual-cpp.md)
