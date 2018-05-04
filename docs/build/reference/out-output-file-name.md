---
title: -OUT (имя выходного файла) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.OutputFile
- /out
dev_langs:
- C++
helpviewer_keywords:
- output files, name linker option
- -OUT linker option
- OUT linker option
- /OUT C++ linker option
- linker [C++], output files
ms.assetid: 976210a4-e51f-4cfb-af5e-c16344455834
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0fd9ec1b1631104355e076071370f627a36b4037
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="out-output-file-name"></a>/OUT (имя выходного файла)
```  
/OUT:filename  
```  
  
## <a name="remarks"></a>Примечания  
 Здесь:  
  
 *filename*  
 Пользовательское имя для выходного файла. Он заменяет имя по умолчанию.  
  
## <a name="remarks"></a>Примечания  
 Параметр/OUT переопределяет стандартное имя и расположение программы, создаваемой компоновщиком.  
  
 По умолчанию компоновщик формирует имя файла, с помощью базового имени первого указанного файла OBJ и соответствующего расширения (.exe или .dll).  
  
 Этот параметр по умолчанию базовое имя для сопоставления MAPFILE или импорта библиотеки. Дополнительные сведения см. в разделе [Создание файла сопоставления](../../build/reference/map-generate-mapfile.md) (/ MAP) и [/IMPLIB](../../build/reference/implib-name-import-library.md).  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [задание свойств проекта Visual C++](../../ide/working-with-project-properties.md).  
  
2.  Нажмите кнопку **компоновщика** папки.  
  
3.  Нажмите кнопку **Общие** страницу свойств.  
  
4.  Изменить **выходной файл** свойство.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.OutputFile%2A>.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)