---
title: -NODEFAULTLIB (пропуск библиотек) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.OVERWRITEAllDefaultLibraries
- VC.Project.VCLinkerTool.OVERWRITEDefaultLibraryNames
- /nodefaultlib
dev_langs:
- C++
helpviewer_keywords:
- default libraries, removing
- -NODEFAULTLIB linker option
- libraries, ignore
- NODEFAULTLIB linker option
- /NODEFAULTLIB linker option
- ignore libraries linker option
ms.assetid: 7270b673-6711-468e-97a7-c2925ac2be6e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 51caac10218d5f4d1787b2256875001ac32dc2b9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="nodefaultlib-ignore-libraries"></a>Параметр /NODEFAULTLIB (пропуск библиотек)
```  
/NODEFAULTLIB[:library]   
```  
  
## <a name="remarks"></a>Примечания  
 Здесь:  
  
 *Библиотека*  
 Библиотека, компоновщиком пропускать при разрешении внешних ссылок.  
  
## <a name="remarks"></a>Примечания  
 Параметр/NODEFAULTLIB предписывает компоновщику удалить один или несколько стандартных библиотек из списка библиотек, в которых осуществляется поиск при разрешении внешних ссылок.  
  
 Чтобы создать OBJ-файл, который не содержит ссылки на библиотеки по умолчанию, используйте [/Zl (пропустить имя библиотеки по умолчанию)](../../build/reference/zl-omit-default-library-name.md).  
  
 По умолчанию параметр/NODEFAULTLIB удаляет все стандартные библиотеки из списка библиотек, в которых осуществляется поиск при разрешении внешних ссылок. Необязательный *библиотеки* параметр позволяет удалить указанных библиотек из списка библиотек, он выполняет поиск при разрешении внешних ссылок. Укажите параметр/NODEFAULTLIB для всех библиотек, которые требуется исключить.  
  
 При разрешении ссылок на внешние определения поиск сначала в библиотеках, которые явно не указан, то по умолчанию библиотек, указанных с помощью параметра/DEFAULTLIB, а затем в стандартных библиотек в OBJ-файлы.  
  
 / Параметр NODEFAULTLIB:*библиотеки* переопределяет [/DEFAULTLIB:](../../build/reference/defaultlib-specify-default-library.md)*библиотеки* при же *библиотеки* указано как имя.  
  
 Если используется параметр/NODEFAULTLIB, например, для построения программы без библиотеки времени выполнения языка C, необходимо также использовать [/Entry](../../build/reference/entry-entry-point-symbol.md) для указания точки входа (функция) в программе. Дополнительные сведения см. в разделе [Функции библиотеки CRT](../../c-runtime-library/crt-library-features.md).  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [задание свойств проекта Visual C++](../../ide/working-with-project-properties.md).  
  
2.  Нажмите кнопку **компоновщика** папки.  
  
3.  Нажмите кнопку **ввода**страницу свойств.  
  
4.  Выберите **игнорировать все стандартные библиотеки** свойства или указать список библиотек, которые необходимо пропустить в **Игнорировать указанную библиотеку** свойство. **Командной строки** страницы свойств будет показано влияние изменения, внесенные в эти свойства.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом  
  
-   См. разделы <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreDefaultLibraryNames%2A> и <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreAllDefaultLibraries%2A>.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)