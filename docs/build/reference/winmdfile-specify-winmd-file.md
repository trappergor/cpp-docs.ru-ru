---
title: -WINMDFILE (укажите файл winmd) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.GenerateWindowsMetadataFile
dev_langs:
- C++
ms.assetid: 062b41b3-14d6-432c-a361-fdb66e918931
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4eaf1bfc805db568a012c28d66361bbd99745a95
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="winmdfile-specify-winmd-file"></a>/WINMDFILE (укажите файл winmd)
Задает имя файла для выходного файла метаданных среды выполнения Windows (.winmd), созданный [/WINMD](../../build/reference/winmd-generate-windows-metadata.md) компоновщика.  
  
```  
/WINMDFILE:filename  
```  
  
## <a name="remarks"></a>Примечания  
 Используйте значение, которое указано в `filename` для переопределения имени winmd-файла по умолчанию (`binaryname`.winmd). Обратите внимание, что вы не добавляете «.winmd» `filename`.  Если несколько значений в списке на **/WINMDFILE** командной строки, последнее из них имеет более высокий приоритет.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Выберите **компоновщика** папки.  
  
3.  Выберите **метаданных Windows** страницу свойств.  
  
4.  В **файл метаданных Windows** введите расположение файла.  
  
## <a name="see-also"></a>См. также  
 [/ WINMD (создавать метаданные Windows)](../../build/reference/winmd-generate-windows-metadata.md)   
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)