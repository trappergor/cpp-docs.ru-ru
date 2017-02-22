---
title: "Макросы для команд и свойств построения | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.GenerateXMLDocumentationFiles"
  - "VC.Project.VCCLCompilerTool.XMLDocumentationFileName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "$(ConfigurationName)- макрос"
  - "$(DevEnvDir) - макрос"
  - "$(FrameworkDir) - макрос"
  - "$(FrameworkSDKDir) - макрос"
  - "$(FrameworkVersion) - макрос"
  - "$(FxCopDir) - макрос"
  - "$(Inherit) - макрос"
  - "$(InputDir) -макрос"
  - "$(InputExt) -макрос"
  - "$(InputFileName) - макрос"
  - "$(InputName) - макрос"
  - "$(InputPath) - макрос"
  - "$(IntDir) - макрос"
  - "$(NoInherit) - макрос"
  - "$(OutDir) - макрос"
  - "$(ParentName) - макрос"
  - "$(PlatformName) -макрос"
  - "$(ProjectDir) -макрос"
  - "$(ProjectExt) - макрос"
  - "$(ProjectFileName) - макрос"
  - "$(ProjectName) - макрос"
  - "$(ProjectPath) - макрос"
  - "$(References) - макрос"
  - "$(RemoteMachine) - макрос"
  - "$(RootNamespace) - макрос"
  - "$(SafeRootNamespace) - макрос"
  - "$(SolutionDir) - макрос"
  - "$(SolutionExt) - макрос"
  - "$(SolutionFileName) - макрос"
  - "$(SolutionName) - макрос"
  - "$(SolutionPath) - макрос"
  - "$(StopEvaluating) - макрос"
  - "$(TargetDir) - макрос"
  - "$(TargetExt) - макрос"
  - "$(TargetFileName) - макрос"
  - "$(TargetName) - макрос"
  - "$(TargetPath) - макрос"
  - "$(VCInstallDir) - макрос"
  - "$(VSInstallDir) - макрос"
  - "$(WebDeployPath) - макрос"
  - "$(WebDeployRoot) - макрос"
  - "макрос построения [C++]"
  - "построения [C++], макросы"
  - "$(ConfigurationName)- макрос ConfigurationName"
  - "$(DevEnvDir) - макрос DevEnvDir"
  - "$(FrameworkDir) - макрос FrameworkDir"
  - "$(FrameworkSDKDir) - макрос FrameworkSDKDir"
  - "FrameworkVersion - макрос $(FrameworkVersion)"
  - "$(FxCopDir) - макрос FxCopDir"
  - "$(Inherit) - макрос Inherit"
  - "$(InputDir) - макрос InputDir"
  - "$(InputExt) - макрос InputExt"
  - "$(InputFileName) - макрос InputFileName"
  - "$(InputName) - макрос InputName"
  - "$(InputPath) - макрос InputPath"
  - "$(IntDir) - макрос IntDir"
  - "макросы [C++], макрос построения"
  - "$(NoInherit) - макрос NoInherit"
  - "$(OutDir) - макрос OutDir"
  - "$(ParentName) - макрос ParentName"
  - "$(PlatformName) - макрос PlatformName"
  - "$(ProjectDir) - макрос ProjectDir"
  - "$(ProjectExt) - макрос ProjectExt"
  - "$(ProjectFileName) - макрос ProjectFileName"
  - "$(ProjectName) - макрос ProjectName"
  - "$(ProjectPath) - макрос ProjectPath"
  - "свойства [C++], макрос свойств построение"
  - "$(References) - макрос References"
  - "$(RemoteMachine) - макрос RemoteMachine"
  - "$(RootNamespace) - макрос RootNamespace"
  - "$(SafeRootNamespace) - макрос SafeRootNamespace"
  - "$(SolutionDir) - макрос SolutionDir"
  - "$(SolutionExt) - макрос SolutionExt"
  - "SolutionFileName - макрос $(SolutionFileName)"
  - "$(SolutionName) - макрос SolutionName"
  - "$(SolutionPath) - макрос SolutionPath"
  - "$(StopEvaluating) - макрос StopEvaluating"
  - "$(TargetDir) - макрос TargetDir"
  - "$(TargetExt) - макрос TargetExt"
  - "TargetFileName - макрос $(TargetFileName)"
  - "$(TargetName) - макрос TargetName"
  - "$(TargetPath) - макрос TargetPath"
  - "$(VCInstallDir) - макрос VCInstallDir"
  - "$(VSInstallDir) - макрос VSInstallDir"
  - "$(WebDeployPath) - макрос WebDeployPath"
  - "$(WebDeployRoot) - макрос WebDeployRoot"
ms.assetid: 239bd708-2ea9-4687-b264-043f1febf98b
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# Макросы для команд и свойств построения
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Эти макросы можно использовать в любом месте диалогового окна **Страницы свойств** проекта, где допустимы строки. В этих макросах регистр не учитывается.  
  
 Для отображения доступных макросов в столбце справа от имени свойства щелкните стрелку раскрывающегося списка. Если доступен пункт **Изменить**, щелкните его и в диалоговом окне редактирования выберите **Макросы**. Дополнительные сведения см. в разделе **Specifying User\-Defined Values** статьи [Страницы свойств](../ide/property-pages-visual-cpp.md).  
  
 Макросы, помеченные как "нерекомендуемые", больше не используются или были заменены эквивалентным [макросом метаданных элемента](../Topic/ItemMetadata%20Element%20\(MSBuild\).md) \(**%\(***имя***\)**\). Макросы, помеченные как "не рекомендуется; перенесены", также считаются устаревшими. Кроме того, если проект, содержащий макрос, переносится из Visual Studio 2008, Visual Studio преобразует макрос в эквивалентный текущий макрос.  
  
|Макрос|Описание|  
|------------|--------------|  
|**$\(RemoteMachine\)**|Задайте значение свойства **Remote Machine**  на странице свойств отладки. Дополнительные сведения см. в разделе [Изменение параметров проекта для конфигурации отладки C или C\+\+](../Topic/Project%20Settings%20for%20a%20C++%20Debug%20Configuration.md).|  
|**$\(Configuration\)**|Имя текущей конфигурации проекта \(например, Debug\).|  
|**$\(Platform\)**|Имя текущей платформы проекта \(например, Win32\).|  
|**$\(ParentName\)**|\(Не рекомендуется.\) Имя элемента, содержащего данный элемент проекта. Это будет имя родительской папки или имя проекта.|  
|**$\(RootNameSpace\)**|Пространство имен \(при наличии\), содержащее приложение.|  
|**$\(IntDir\)**|Путь к каталогу, заданному для промежуточных файлов. Если это относительный путь, промежуточные файлы передаются по этому пути, добавленному к каталогу проекта. Этот путь должен содержать косую черту в конце. Путь разрешается в значение для свойства **Intermediate Directory**. Не используйте **$\(OutDir\)** для определения этого свойства.|  
|**$\(OutDir\)**|Путь к каталогу выходных файлов. Если это относительный путь, выходные файлы передаются по этому пути, добавленному к каталогу проекта. Этот путь должен содержать косую черту в конце. Путь разрешается в значение для свойства **Output Directory**. Не используйте **$\(IntDir\)** для определения этого свойства.|  
|**$\(DevEnvDir\)**|Папка установки Visual Studio \(определяется как диск \+ путь\); включает обратную косую черту "\\".|  
|**$\(InputDir\)**|\(Не рекомендуется; перенесено.\) Каталог входного файла \(определяется как диск \+ путь\); включает обратную косую черту "\\". Если проект является входными данными, этот макрос эквивалентен **$\(ProjectDir\)**.|  
|**$\(InputPath\)**|\(Не рекомендуется; перенесено.\) Абсолютный путь к входному файлу \(определяется как диск \+ путь \+ базовое имя \+ расширение файла\). Если проект является входными данными, этот макрос эквивалентен **$\(ProjectPath\)**.|  
|**$\(InputName\)**|\(Не рекомендуется; перенесено.\) Базовое имя входного файла. Если проект является входными данными, этот макрос эквивалентен **$\(ProjectName\)**.|  
|**$\(InputFileName\)**|\(Не рекомендуется; перенесено.\) Имя входного файла \(определяется как базовое имя \+ расширение файла\). Если проект является входными данными, этот макрос эквивалентен **$\(ProjectFileName\)**.|  
|**$\(InputExt\)**|\(Не рекомендуется; перенесено.\) Расширение имени входного файла. Включает символ "." перед расширением файла. Если проект является входными данными, этот макрос эквивалентен **$\(ProjectExt\)**.|  
|**$\(ProjectDir\)**|Каталог проекта \(определяется как диск \+ путь\); включает обратную косую черту "\\".|  
|**$\(ProjectPath\)**|Абсолютный путь к проекту \(определяется как диск \+ путь \+ базовое имя \+ расширение файла\).|  
|**$\(ProjectName\)**|Базовое имя проекта.|  
|**$\(ProjectFileName\)**|Имя файла проекта \(определяется как базовое имя \+ расширение файла\).|  
|**$\(ProjectExt\)**|Расширение файла проекта. Включает символ "." перед расширением файла.|  
|**$\(SolutionDir\)**|Каталог решения \(определяется как диск \+ путь\); включает обратную косую черту "\\".|  
|**$\(SolutionPath\)**|Абсолютный путь к решению \(определяется как диск \+ путь \+ базовое имя \+ расширение файла\).|  
|**$\(SolutionName\)**|Базовое имя решения.|  
|**$\(SolutionFileName\)**|Имя файла решения \(определяется как базовое имя \+ расширение файла\).|  
|**$\(SolutionExt\)**|Расширение файла решения. Включает символ "." перед расширением файла.|  
|**$\(TargetDir\)**|Каталог основного выходного файла для сборки \(определяется как диск \+ путь\); включает обратную косую черту "\\".|  
|**$\(TargetPath\)**|Абсолютный путь к основному выходному файлу для сборки \(определяется как диск \+ путь \+ базовое имя \+ расширение файла\).|  
|**$\(TargetName\)**|Базовое имя основного выходного файла сборки.|  
|**$\(TargetFileName\)**|Имя основного выходного файла для сборки \(определяется как базовое имя \+ расширение файла\).|  
|**$\(TargetExt\)**|Расширение имени основного выходного файла сборки. Включает символ "." перед расширением файла.|  
|**$\(VSInstallDir\)**|Каталог, в котором установлено программное обеспечение Visual Studio.<br /><br /> Это свойство содержит версию целевой платформы Visual Studio, которая может отличаться от платформы Visual Studio компьютера. Например, при построении с помощью `$(PlatformToolset) = v110` свойство **$\(VSInstallDir\)** содержит путь к установке Visual Studio 2012.|  
|**$\(VCInstallDir\)**|Каталог, в котором установлено программное обеспечение Visual C\+\+.<br /><br /> Это свойство содержит версию целевой платформы Visual C\+\+, которая может отличаться от платформы Visual Studio компьютера. Например, при построении с помощью `$(PlatformToolset) = v90` свойство **$\(VCInstallDir\)** содержит путь к установке Visual C\+\+ 2008.|  
|**$\(FrameworkDir\)**|Каталог, в котором установлена платформа .NET Framework.|  
|**$\(FrameworkVersion\)**|Версия платформы .NET Framework, используемая Visual Studio. В сочетании с **$\(FrameworkDir\)** — полный путь к версии .NET Framework, используемой Visual Studio.|  
|**$\(FrameworkSDKDir\)**|Каталог, в котором установлена платформа .NET Framework. Платформу .NET Framework можно установить в составе Visual Studio или отдельно.|  
|**$\(WebDeployPath\)**|Относительный путь от корня веб\-развертывания до каталога выходных данных проекта. Возвращает значение такого же типа, что и аргумент <xref:Microsoft.VisualStudio.VCProjectEngine.VCWebDeploymentTool.RelativePath%2A>.|  
|**$\(WebDeployRoot\)**|Абсолютный путь к расположению **\<localhost\>**. Например, c:\\inetpub\\wwwroot.|  
|**$\(SafeParentName\)**|\(Не рекомендуется.\) Имя непосредственного родителя в допустимом формате. Например, форма является родителем RESX\-файла.|  
|**$\(SafeInputName\)**|\(Не рекомендуется.\) Имя файла как допустимое имя класса \(без расширения файла\).|  
|**$\(SafeRootNamespace\)**|\(Не рекомендуется.\) Имя пространства имен, в которое мастера проекта будут добавлять код. Это пространство имен будет содержать только те символы, которые разрешены в допустимых идентификаторах C\+\+.|  
|**$\(FxCopDir\)**|Путь к файлу fxcop.cmd. Файл fxcop.cmd устанавливается не со всеми выпусками Visual C\+\+.|  
  
## См. также  
 [Построение проектов C\+\+ в Visual Studio](../ide/building-cpp-projects-in-visual-studio.md)