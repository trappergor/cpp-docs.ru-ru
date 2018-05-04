---
title: -DEFAULTLIB (определение библиотеки по умолчанию) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.DefaultLibraries
- /defaultlib
dev_langs:
- C++
helpviewer_keywords:
- -DEFAULTLIB linker option
- DEFAULTLIB linker option
- /DEFAULTLIB linker option
- libraries, adding to list of
ms.assetid: 6af7ff49-c170-4a13-97e2-2b9ae2de20c9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e48db05ea50917a09e618c782d86dace73a1bf7e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="defaultlib-specify-default-library"></a>/DEFAULTLIB (определение библиотеки по умолчанию)
```  
/DEFAULTLIB:library  
```  
  
## <a name="remarks"></a>Примечания  
 Здесь:  
  
 *Библиотека*  
 Имя библиотеки для поиска при разрешении внешних ссылок.  
  
## <a name="remarks"></a>Примечания  
 Параметр/DEFAULTLIB добавляет единицу *библиотеки* в список библиотек, LINK выполняет поиск при разрешении ссылок. Это библиотека, заданная с/DEFAULTLIB, выполняется после библиотек, указанных в командной строке и перед стандартных библиотек в OBJ-файлы.  
  
 [Игнорировать все стандартные библиотеки](../../build/reference/nodefaultlib-ignore-libraries.md) (/ NODEFAULTLIB) переопределяет параметр/DEFAULTLIB:*библиотеки*. [Игнорировать библиотеки](../../build/reference/nodefaultlib-ignore-libraries.md) (/ NODEFAULTLIB:*библиотеки*) переопределяет параметр/DEFAULTLIB:*библиотеки* при же *библиотеки* имя указан в обеих.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio  
  
-   Этот параметр не доступен из среды разработки Visual Studio. Для добавления библиотеки на этапе компоновки, используйте **Дополнительные зависимости** свойство из **ввода** страницу свойств.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)