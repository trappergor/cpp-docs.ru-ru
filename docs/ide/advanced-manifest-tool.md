---
title: Дополнительно, инструмент манифеста, свойства конфигурации &lt;Projectname&gt; диалоговое окно страниц свойств | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.VCManifestTool.KeyFile
- VC.Project.VCManifestTool.UpdateFileHashes
- VC.Project.VCManifestTool.UpdateFileHashesSearchPath
- VC.Project.VCManifestTool.ValidateSignature
- VC.Project.VCManifestTool.KeyContainer
dev_langs:
- C++
ms.assetid: 3d587366-05ea-4956-a978-313069660735
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 47d4dc3ab325a7346d0e787a15d69d646896827d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="advanced-manifest-tool-configuration-properties-ltprojectnamegt-property-pages-dialog-box"></a>Дополнительно, инструмент манифеста, свойства конфигурации &lt;Projectname&gt; диалоговое окно страниц свойств
Используйте это диалоговое окно позволяет задать дополнительные параметры для [Mt.exe](http://msdn.microsoft.com/library/aa375649).  
  
 Чтобы открыть это диалоговое окно страницы свойств, откройте страницы свойств для проекта или вкладку свойств. Разверните **инструмент манифеста** узле **свойства конфигурации**, а затем выберите **Дополнительно**.  
  
## <a name="uielement-list"></a>Список элементов пользовательского интерфейса  
 **Обновлять хэши файлов**  
 / Hashupdate для указания, что инструмент манифеста будет вычислять хэш файлов, указанных в `<file>` элементы и только затем хэш атрибуты с вычисленным значением.  
  
 **Обновление пути поиска хэшей файлов**  
 Указывает путь поиска для файлов, которые упоминаются в `<file>` элементов. Этот параметр также/hashupdate.  
  
## <a name="see-also"></a>См. также  
 [\<Файл > элемент](/visualstudio/deployment/file-element-clickonce-application)   
 [Манифест приложения ClickOnce](/visualstudio/deployment/clickonce-application-manifest)   
 [Страницы свойств средства манифестов](../ide/manifest-tool-property-pages.md)   
 [Работа со свойствами проектов](../ide/working-with-project-properties.md)   