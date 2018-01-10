---
title: "-WINMDFILE (укажите файл winmd) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VC.Project.VCLinkerTool.GenerateWindowsMetadataFile
dev_langs: C++
ms.assetid: 062b41b3-14d6-432c-a361-fdb66e918931
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 153e5c0bd42b6fdba59e309483f25f09b86fe9fa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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