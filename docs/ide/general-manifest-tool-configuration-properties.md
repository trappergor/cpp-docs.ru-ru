---
title: Свойства конфигурации для инструмента манифеста (Visual C++) | Документы Майкрософт
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
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33329092"
---
# <a name="general-manifest-tool-configuration-properties-ltprojectnamegt-property-pages-dialog-box"></a>Диалоговое окно страниц свойств &lt;Имя_проекта&gt; "Свойства конфигурации", "Инструмент манифеста", "Общие"
Используйте это диалоговое окно для указания общих параметров для [Mt.exe](http://msdn.microsoft.com/library/aa375649).  
  
 Чтобы открыть это диалоговое окно страницы свойств, откройте страницы свойств для своего проекта или свою страницу свойств. Разверните узел**Инструмент манифеста** в области **Свойства конфигурации**, а затем выберите элемент **Общие**.  
  
## <a name="uielement-list"></a>Список элементов пользовательского интерфейса  
 **Отключить загрузочное объявление**  
 **Да (/nologo)** указывает, что стандартные сведения об авторских правах Майкрософт будут скрыты при запуске инструмента манифеста. Используйте этот параметр, чтобы скрыть нежелательный вывод в файлах журнала, при выполнении mt.exe в рамках процесса сборки или из среды сборки.  
  
 **Подробный вывод**  
 **Да (/verbose)** указывает, что при создании манифеста будут отображаться дополнительные сведения о сборке.  
  
 **Удостоверение сборки**  
 Использует параметр /identity для указания строки удостоверения, которая состоит из атрибутов для [элемента \<assemblyIdentity>](/visualstudio/deployment/assemblyidentity-element-clickonce-application). Строка удостоверения начинается со значения для атрибута `name`, за которым следуют пары *атрибут* = *значение*. Атрибуты в строке удостоверения разделяются запятыми.  
  
 Пример строки удостоверения:  
  
 `Microsoft.Windows.Common-Controls, processorArchitecture=x86, version=6.0.0.0, type=win32, publicKeyToken=6595b64144ccf1df`  
  
## <a name="see-also"></a>См. также  
 [Манифест приложения ClickOnce](/visualstudio/deployment/clickonce-application-manifest)   
 [Страницы свойств инструмента манифеста](../ide/manifest-tool-property-pages.md)   
 [Работа со свойствами проектов](../ide/working-with-project-properties.md)   