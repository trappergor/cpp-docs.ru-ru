---
title: -NOENTRY (точка входа) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.ResourceOnlyDLL
- /noentry
dev_langs:
- C++
helpviewer_keywords:
- entry points [C++], linker specifying
- -NOENTRY linker option
- resource-only DLLs [C++], creating
- NOENTRY linker option
- /NOENTRY linker option [C++]
- DLLs [C++], creating
ms.assetid: 0214dd41-35ad-43ab-b892-e636e038621a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 44f35c995a0c839fdc0d4ccf3d286e332793cf70
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32374041"
---
# <a name="noentry-no-entry-point"></a>/NOENTRY (точка входа отсутствует)
```  
/NOENTRY  
```  
  
## <a name="remarks"></a>Примечания  
 Параметр /NOENTRY требуется для создания DLL-библиотеки, содержащей только ресурсы, без исполняемого кода. Дополнительные сведения см. в разделе [Создание библиотеки DLL Resource-Only](../../build/creating-a-resource-only-dll.md).  
  
 Используйте этот параметр, чтобы LINK не добавлял ссылку на `_main` в DLL.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [задание свойств проекта Visual C++](../../ide/working-with-project-properties.md).  
  
2.  Выберите **компоновщика** папки.  
  
3.  Выберите **Дополнительно** страницу свойств.  
  
4.  Изменить **не точка входа** свойство.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом  
  
1.  См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ResourceOnlyDLL%2A>.  
  
## <a name="see-also"></a>См. также  
 [Создание Библиотеку ресурсов](../../build/creating-a-resource-only-dll.md)   
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)