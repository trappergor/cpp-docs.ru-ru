---
title: -LIBPATH (дополнительный параметр Libpath) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /libpath
- VC.Project.VCLinkerTool.AdditionalLibraryDirectories
dev_langs:
- C++
helpviewer_keywords:
- LIBPATH linker option
- /LIBPATH linker option
- Additional Libpath linker option
- environment library path override
- -LIBPATH linker option
- library path linker option
ms.assetid: 7240af0b-9a3d-4d53-8169-2a92cd6958ba
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5ccb94ad20735e81fc3d83f757cc0265cdc32169
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32372884"
---
# <a name="libpath-additional-libpath"></a>Параметр /LIBPATH (дополнительный параметр libpath)
```  
/LIBPATH:dir  
```  
  
## <a name="remarks"></a>Примечания  
 Здесь:  
  
 `dir`  
 Указывает путь, компоновщик будет поиска перед поиском по пути, указанного в параметре среды LIB.  
  
## <a name="remarks"></a>Примечания  
 Используйте параметр/LIBPATH, чтобы переопределить путь к библиотеке среды. Компоновщик будет сначала выполнить поиск в каталоге, указанном этим параметром и выполните поиск в каталоге, указанном в переменной среды LIB. Можно указать только один каталог для каждого вводимого параметра/LIBPATH. Если вы хотите указать несколько каталогов, необходимо указать несколько параметров/LIBPATH. Затем компоновщик выполняет поиск указанных каталогах в порядке.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [задание свойств проекта Visual C++](../../ide/working-with-project-properties.md).  
  
2.  Нажмите кнопку **компоновщика** папки.  
  
3.  Нажмите кнопку **Общие** страницу свойств.  
  
4.  Изменить **Дополнительные каталоги библиотек** свойство.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalLibraryDirectories%2A>.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)