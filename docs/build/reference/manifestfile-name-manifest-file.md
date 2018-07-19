---
title: -MANIFESTFILE (имя файла манифеста) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.ManifestFile
dev_langs:
- C++
helpviewer_keywords:
- MANIFESTFILE linker option
- -MANIFESTFILE linker option
- /MANIFESTFILE linker option
ms.assetid: befa5ab2-a9cf-4c9b-969a-e7b4a930f08d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b95337afc790436187c547bba108da2161b0738b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32373352"
---
# <a name="manifestfile-name-manifest-file"></a>/MANIFESTFILE (Имя файла манифеста)
```  
/MANIFESTFILE:filename  
```  
  
## <a name="remarks"></a>Примечания  
 / MANIFESTFILE позволяет изменить имя файла манифеста по умолчанию.  Имя файла манифеста по умолчанию является имя файла с расширением MANIFEST.  
  
 / MANIFESTFILE окажет никакого воздействия, если также не связана с [/MANIFEST](../../build/reference/manifest-create-side-by-side-assembly-manifest.md).  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Разверните **свойства конфигурации** узла.  
  
3.  Разверните **компоновщика** узла.  
  
4.  Выберите **файл манифеста** страницу свойств.  
  
5.  Изменить **файл манифеста** свойство.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом  
  
1.  См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ManifestFile%2A>.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)