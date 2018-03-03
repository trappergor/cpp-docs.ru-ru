---
title: "Инструмент манифеста изолированного свойства COM (Visual C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCManifestTool.RegistrarScriptFile
- VC.Project.VCManifestTool.ComponentFileName
- VC.Project.VCManifestTool.TypeLibraryFile
- VC.Project.VCManifestTool.ReplacementsFile
dev_langs:
- C++
ms.assetid: 457582b8-cfde-49c0-92e3-3a6b9e8c08eb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fe2098c4caead6ebc9ad4747354ae96f093f2c91
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="isolated-com-manifest-tool-configuration-properties-ltprojectnamegt-property-pages-dialog-box"></a>Изолированные COM, инструмент манифеста, свойства конфигурации, &lt;Projectname&gt; диалоговое окно страниц свойств
Используйте это диалоговое окно предназначено для указания **изолированная модель COM** параметры для [Mt.exe](http://msdn.microsoft.com/library/aa375649).  
  
 Чтобы открыть это диалоговое окно страницы свойств, откройте страницы свойств для проекта или вкладку свойств. Разверните **инструмент манифеста** узле **общие свойства**, а затем выберите **изолированная модель COM**.  
  
## <a name="task-list"></a>список задач  
  
-   [Практическое руководство. Сборка изолированных приложений, использующих компоненты СОМ](../build/how-to-build-isolated-applications-to-consume-com-components.md)  
  
## <a name="uielement-list"></a>Список элементов пользовательского интерфейса  
 **Файл библиотеки типов**  
 Чтобы указать имя файла библиотеки типов (TLB-файл), инструмент манифеста будет использовать для создания файла манифеста, используется параметр/tlb.  
  
 **Файл скрипта регистратора**  
 Используется параметр /rgs, чтобы указать имя файла скрипта регистратора (RGS-файл), инструмент манифеста будет использовать для создания файла манифеста.  
  
 **Имя файла компонента**  
 Используется параметр/DLL для указания имени ресурса, который будет создавать инструмент манифеста. Необходимо ввести значение для этого свойства при значения на **файла библиотеки типов** или **файл скрипта регистратора** указаны.  
  
 **Файл перестановок**  
 Используется параметр /replacements, чтобы указать полный путь к файлу, содержащему значения для замены строк в RGS-файле.  
  
## <a name="see-also"></a>См. также  
 [Изолированные приложения](http://msdn.microsoft.com/library/aa375190)   
 [Манифест приложения ClickOnce](/visualstudio/deployment/clickonce-application-manifest)   
 [Страницы свойств средства манифестов](../ide/manifest-tool-property-pages.md)   
 [Работа со свойствами проектов](../ide/working-with-project-properties.md)   