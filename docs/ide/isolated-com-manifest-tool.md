---
title: "Диалоговое окно страниц свойств &lt;Имя_проекта&gt; &#171;Свойства конфигурации&#187;, &#171;Инструмент манифеста&#187;, &#171;Изолированная модель COM&#187; | Microsoft Docs"
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
  - "VC.Project.VCManifestTool.RegistrarScriptFile"
  - "VC.Project.VCManifestTool.ComponentFileName"
  - "VC.Project.VCManifestTool.TypeLibraryFile"
  - "VC.Project.VCManifestTool.ReplacementsFile"
dev_langs: 
  - "C++"
ms.assetid: 457582b8-cfde-49c0-92e3-3a6b9e8c08eb
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Диалоговое окно страниц свойств &lt;Имя_проекта&gt; &#171;Свойства конфигурации&#187;, &#171;Инструмент манифеста&#187;, &#171;Изолированная модель COM&#187;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Данное диалоговое окно используется для задания параметров **Изолированного COM** для файла [Mt.exe](http://msdn.microsoft.com/library/aa375649).  
  
 Чтобы открыть диалоговое окно страницы свойств, откройте страницу свойств проекта или вкладку свойств.  В разделе **Общие свойства** разверните узел **Инструмент манифеста**, а затем выберите **Изолированный COM**.  
  
## Список задач  
  
-   [Практическое руководство. Построение изолированных приложений, использующих компоненты СОМ](../Topic/How%20to:%20Build%20Isolated%20Applications%20to%20Consume%20COM%20Components.md)  
  
## Список элементов пользовательского интерфейса  
 **Файл библиотеки типов**  
 Используется ключом \/tlb для указания имени файла библиотеки типов \(TLB\-файла\), который будет использоваться инструментом манифеста при создании файла манифеста.  
  
 **Файл скрипта регистрации**  
 Используется ключом \/rgs для указания имени файла скрипта регистрации \(RGS\-файла\), который будет использоваться инструментом манифеста при создании файла манифеста.  
  
 **Имя файла компонента**  
 Используется ключом \/dll для указания имени ресурса, который будет создавать инструмент манифеста.  Значение данного свойства необходимо указывать, если задан **Файл библиотеки типов** или **Файл скрипта регистрации**.  
  
 **Файл перестановок**  
 Используется ключом \/replacements для указания полного пути к файлу, содержащему значения для замены строк в RGS\-файле.  
  
## См. также  
 [Изолированные приложения](http://msdn.microsoft.com/library/aa375190)   
 [Параллельные сборки](_win32_side_by_side_assemblies)   
 [Манифест приложения ClickOnce](../Topic/ClickOnce%20Application%20Manifest.md)   
 [Страницы свойств средства манифестов](../ide/manifest-tool-property-pages.md)   
 [Открытие свойств страниц проекта](../misc/how-to-open-project-property-pages.md)   
 [Практическое руководство: изменение страниц свойств в проекте](../misc/how-to-edit-project-property-sheets.md)