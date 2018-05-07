---
title: Манифест свойства конфигурации средства (Visual C++) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.VCManifestTool.MergeRulesFile
- VC.Project.VCManifestTool.UseUnicodeResponseFiles
- VC.Project.VCManifestTool.SuppressStartupBanner
- VC.Project.VCManifestTool.UseFAT32Workaround
- VC.Project.VCManifestTool.VerboseOutput
- VC.Project.VCManifestTool.AssemblyIdentity
dev_langs:
- C++
ms.assetid: b99368a5-6819-482c-a06e-f2409290cfd1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1953e7c37c07f66845510efe037015a537aa7baa
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="general-manifest-tool-configuration-properties-ltprojectnamegt-property-pages-dialog-box"></a>Общие, инструмент манифеста, свойства конфигурации &lt;Projectname&gt; диалоговое окно страниц свойств
Используйте это диалоговое окно позволяет задать общие параметры для [Mt.exe](http://msdn.microsoft.com/library/aa375649).  
  
 Чтобы открыть это диалоговое окно страницы свойств, откройте страницы свойств для проекта или вкладку свойств. Разверните **инструмент манифеста** узле **свойства конфигурации**, а затем выберите **Общие**.  
  
## <a name="uielement-list"></a>Список элементов пользовательского интерфейса  
 **Отключить загрузочное объявление**  
 **Да (/ nologo)** указывает, что стандартные сведения об авторских правах Майкрософт будут скрыты при запуске инструмента манифеста. Используйте этот параметр для отключения нежелательного вывода в файлах журнала, при выполнении mt.exe как часть процесса построения или из среды разработки.  
  
 **Подробный вывод**  
 **Да (/ verbose)** указывает, что Дополнительные сведения о построении будут отображаться во время создания манифеста.  
  
 **Удостоверение сборки**  
 Использует параметр /identity для указания Строка удостоверения, который состоит из атрибутов для [ \<assemblyIdentity > элемент](/visualstudio/deployment/assemblyidentity-element-clickonce-application). Строка удостоверения начинается со значения для `name` атрибута и следуют *атрибута* = *значение* пары. Атрибуты в строке удостоверения разделяются запятыми.  
  
 Ниже приведен пример строки удостоверения.  
  
 `Microsoft.Windows.Common-Controls, processorArchitecture=x86, version=6.0.0.0, type=win32, publicKeyToken=6595b64144ccf1df`  
  
## <a name="see-also"></a>См. также  
 [Манифест приложения ClickOnce](/visualstudio/deployment/clickonce-application-manifest)   
 [Страницы свойств средства манифестов](../ide/manifest-tool-property-pages.md)   
 [Работа со свойствами проектов](../ide/working-with-project-properties.md)   