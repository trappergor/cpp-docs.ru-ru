---
title: Общие макросы для команд и свойств построения | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.VCCLCompilerTool.GenerateXMLDocumentationFiles
- VC.Project.VCCLCompilerTool.XMLDocumentationFileName
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9b94347e48a7b8b134915456c92aea3397f97a1b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="common-macros-for-build-commands-and-properties"></a>Общие макросы для команд и свойств построения
В зависимости от параметров установки Visual Studio можно сделать сотни макросы доступными для вас. Они соответствуют свойства MSBuild, которые устанавливаются по умолчанию, или в файлах с расширением PROPS или .targets или в параметрах проекта. Эти макросы можно использовать в любом месте диалогового окна **Страницы свойств** проекта, где допустимы строки. В этих макросах регистр не учитывается.  
  
 Для отображения доступных макросов в столбце справа от имени свойства щелкните стрелку раскрывающегося списка. Если доступен пункт **Изменить** , щелкните его и в диалоговом окне редактирования выберите **Макросы**. Дополнительные сведения см. в разделе **Specifying User-Defined Values** статьи [Страницы свойств](../ide/property-pages-visual-cpp.md).  
  
 Макросы, помеченные как «Нерекомендуемые» больше не используются или были заменены эквивалентным [макросом метаданных элемента](/visualstudio/msbuild/itemmetadata-element-msbuild) (**%(***имя***)**). Макросы, помеченные как "не рекомендуется; перенесены", также считаются устаревшими. Кроме того, если проект, содержащий макрос, переносится из Visual Studio 2008, Visual Studio преобразует макрос в эквивалентный текущий макрос.  
  
 Следующая таблица описывает часто используемые подмножество доступных макросов. Этот список не является исчерпывающим. Дополнительные сведения о том, как создаются и используются как макросы в файлы с расширением VCXPROJ, с расширением PROPS и .targets определения свойств MSBuild см [свойства MSBuild](/visualstudio/msbuild/msbuild-properties).  
  
|Макрос|Описание|  
|-----------|-----------------|  
|**$(RemoteMachine)**|Задайте значение свойства **Remote Machine** на странице свойств отладки. Дополнительные сведения см. в разделе [Изменение параметров проекта для конфигурации отладки C или C++](/visualstudio/debugger/project-settings-for-a-cpp-debug-configuration) .|  
|**$(Configuration)**|Имя текущей конфигурации проекта, например "Debug".|  
|**$(Platform)**|Имя текущей платформы проекта, например, «Win32».|  
|**$(ParentName)**|(Не рекомендуется.) Имя элемента, содержащего данный элемент проекта. Это будет имя родительской папки или имя проекта.|  
|**$(RootNameSpace)**|Пространство имен (при наличии), содержащее приложение.|  
|**$(IntDir)**|Путь к каталогу, заданному для промежуточных файлов. Если это относительный путь, промежуточные файлы передаются по этому пути, добавленному к каталогу проекта. Этот путь должен содержать косую черту в конце. Путь разрешается в значение для свойства **Intermediate Directory** . Не используйте **$(OutDir)** для определения этого свойства.|  
|**$(OutDir)**|Путь к каталогу выходных файлов. Если это относительный путь, выходные файлы передаются по этому пути, добавленному к каталогу проекта. Этот путь должен содержать косую черту в конце. Путь разрешается в значение для свойства **Output Directory** . Не используйте **$(IntDir)** для определения этого свойства.|  
|**$(DevEnvDir)**|Папка установки Visual Studio (определяется как диск + путь); включает обратную косую черту "\\".|  
|**$(InputDir)**|(Не рекомендуется; перенесено.) Каталог входного файла (определяется как диск + путь); включает обратную косую черту "\\". Если проект является входными данными, этот макрос эквивалентен **$(ProjectDir)**.|  
|**$(InputPath)**|(Не рекомендуется; перенесено.) Абсолютный путь к входному файлу (определяется как диск + путь + базовое имя + расширение файла). Если проект является входными данными, этот макрос эквивалентен **$(ProjectPath)**.|  
|**$(InputName)**|(Не рекомендуется; перенесено.) Базовое имя входного файла. Если проект является входными данными, этот макрос эквивалентен **$(ProjectName)**.|  
|**$(InputFileName)**|(Не рекомендуется; перенесено.) Имя входного файла (определяется как базовое имя + расширение файла). Если проект является входными данными, этот макрос эквивалентен **$(ProjectFileName)**.|  
|**$(InputExt)**|(Не рекомендуется; перенесено.) Расширение имени входного файла. Включает символ "." перед расширением файла. Если проект является входными данными, этот макрос эквивалентен **$(ProjectExt)**.|  
|**$(ProjectDir)**|Каталог проекта (определяется как диск + путь); включает обратную косую черту "\\".|  
|**$(ProjectPath)**|Абсолютный путь к проекту (определяется как диск + путь + базовое имя + расширение файла).|  
|**$(ProjectName)**|Базовое имя проекта.|  
|**$(ProjectFileName)**|Имя файла проекта (определяется как базовое имя + расширение файла).|  
|**$(ProjectExt)**|Расширение файла проекта. Включает символ "." перед расширением файла.|  
|**$ (Solutiondir)**|Каталог решения (определяется как диск + путь); включает обратную косую черту "\\". Определен только в том случае, если построение решения в Интегрированной среде разработки.|  
|**$(SolutionPath)**|Абсолютный путь к решению (определяется как диск + путь + базовое имя + расширение файла). Определен только в том случае, если построение решения в Интегрированной среде разработки.|  
|**$(SolutionName)**|Базовое имя решения. Определен только в том случае, если построение решения в Интегрированной среде разработки.|  
|**$(SolutionFileName)**|Имя файла решения (определяется как базовое имя + расширение файла). Определен только в том случае, если построение решения в Интегрированной среде разработки.|  
|**$(SolutionExt)**|Расширение файла решения. Включает символ "." перед расширением файла. Определен только в том случае, если построение решения в Интегрированной среде разработки.|  
|**$(TargetDir)**|Каталог основного выходного файла для сборки (определяется как диск + путь); включает обратную косую черту "\\".|  
|**$(TargetPath)**|Абсолютный путь к основному выходному файлу для сборки (определяется как диск + путь + базовое имя + расширение файла).|  
|**$(TargetName)**|Базовое имя основного выходного файла сборки.|  
|**$(TargetFileName)**|Имя основного выходного файла для сборки (определяется как базовое имя + расширение файла).|  
|**$(TargetExt)**|Расширение имени основного выходного файла сборки. Включает символ "." перед расширением файла.|  
|**$(VSInstallDir)**|Каталог, в котором установлено программное обеспечение Visual Studio.<br /><br /> Это свойство содержит версию целевой платформы Visual Studio, которая может отличаться от платформы Visual Studio компьютера. Например, при построении с помощью `$(PlatformToolset) = v110`свойство **$(VSInstallDir)** содержит путь к установке Visual Studio 2012.|  
|**$(VCInstallDir)**|Каталог, в котором установлено программное обеспечение Visual C++.<br /><br /> Это свойство содержит версию целевой платформы Visual C++, которая может отличаться от платформы Visual Studio компьютера. Например, при построении с помощью `$(PlatformToolset) = v140`, **$(VCInstallDir)** содержит путь к установке Visual C++ 2015.|  
|**$(FrameworkDir)**|Каталог, в котором установлена платформа .NET Framework.|  
|**$(FrameworkVersion)**|Версия платформы .NET Framework, используемая Visual Studio. В сочетании с **$(FrameworkDir)**— полный путь к версии .NET Framework, используемой Visual Studio.|  
|**$(FrameworkSDKDir)**|Каталог, в котором установлена платформа .NET Framework. Платформу .NET Framework можно установить в составе Visual Studio или отдельно.|  
|**$(WebDeployPath)**|Относительный путь от корня веб-развертывания до каталога выходных данных проекта. Возвращает значение такого же типа, что и аргумент <xref:Microsoft.VisualStudio.VCProjectEngine.VCWebDeploymentTool.RelativePath%2A>.|  
|**$(WebDeployRoot)**|Абсолютный путь к расположению  **\<localhost >**. Например, c:\inetpub\wwwroot.|  
|**$(SafeParentName)**|(Не рекомендуется.) Имя непосредственного родителя в допустимом формате. Например, форма является родителем RESX-файла.|  
|**$(SafeInputName)**|(Не рекомендуется.) Имя файла как допустимое имя класса (без расширения файла).|  
|**$(SafeRootNamespace)**|(Не рекомендуется.) Имя пространства имен, в которое мастера проекта будут добавлять код. Это пространство имен будет содержать только те символы, которые разрешены в допустимых идентификаторах C++.|  
|**$(FxCopDir)**|Путь к файлу fxcop.cmd. Файл fxcop.cmd устанавливается не со всеми выпусками Visual C++.|  
  
## <a name="see-also"></a>См. также  
 [Сборка проектов C++ в Visual Studio](../ide/building-cpp-projects-in-visual-studio.md)