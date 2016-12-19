---
title: "Диалоговое окно страниц свойств &lt;Имя_проекта&gt; &#171;Свойства конфигурации&#187;, &#171;Инструмент манифеста&#187;, &#171;Общие&#187; | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCManifestTool.MergeRulesFile"
  - "VC.Project.VCManifestTool.UseUnicodeResponseFiles"
  - "VC.Project.VCManifestTool.SuppressStartupBanner"
  - "VC.Project.VCManifestTool.UseFAT32Workaround"
  - "VC.Project.VCManifestTool.VerboseOutput"
  - "VC.Project.VCManifestTool.AssemblyIdentity"
dev_langs: 
  - "C++"
ms.assetid: b99368a5-6819-482c-a06e-f2409290cfd1
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Диалоговое окно страниц свойств &lt;Имя_проекта&gt; &#171;Свойства конфигурации&#187;, &#171;Инструмент манифеста&#187;, &#171;Общие&#187;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Это диалоговое окно позволяет задать общие параметры для файла [Mt.exe](http://msdn.microsoft.com/library/aa375649).  
  
 Чтобы открыть диалоговое окно страницы свойств, откройте страницу свойств проекта или вкладку свойств.  Разверните узел **Инструмент манифеста** в разделе **Свойства Конфигурации** и выберите **Общие**.  
  
## Список элементов пользовательского интерфейса  
 **Отключить отображение приветствия при загрузке**  
 **Да \(\/nologo\)** указывает, что стандартные сведения об авторских правах Майкрософт будут скрыты при запуске инструмента манифеста.  Этот параметр используется для отключения нежелательного вывода в файлах журнала при запуске программы mt.exe как части процесса построения или из среды построения.  
  
 **Подробный вывод**  
 **Да \(\/verbose\)** указывает, что дополнительные сведения о построении будут отображаться во время создания манифеста.  
  
 **Идентификатор сборки**  
 Использует параметр \/identity для указания строки удостоверения, которая содержит атрибуты для [Элемент \<assemblyIdentity\>](../Topic/%3CassemblyIdentity%3E%20Element%20\(ClickOnce%20Application\).md).  Строка удостоверения начинается со значения для атрибута `name` и продолжается парами "*атрибут* \= *значение*".  Атрибуты в строке удостоверения разделяются запятой.  
  
 Ниже приведен пример строки удостоверения:  
  
 `Microsoft.Windows.Common-Controls, processorArchitecture=x86, version=6.0.0.0, type=win32, publicKeyToken=6595b64144ccf1df`  
  
## См. также  
 [Манифест приложения ClickOnce](../Topic/ClickOnce%20Application%20Manifest.md)   
 [Страницы свойств средства манифестов](../ide/manifest-tool-property-pages.md)   
 [Открытие свойств страниц проекта](../misc/how-to-open-project-property-pages.md)   
 [Практическое руководство: изменение страниц свойств в проекте](../misc/how-to-edit-project-property-sheets.md)