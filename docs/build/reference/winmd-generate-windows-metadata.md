---
title: "-WINMD (создавать метаданные Windows) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.GenerateWindowsMetadata
dev_langs:
- C++
ms.assetid: bcfb4901-411e-4c9e-9f78-23028b6e5fcc
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7517ec459677659067e80930ee48caccf84d52f3
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="winmd-generate-windows-metadata"></a>/WINMD (создавать метаданные Windows)
Включает создание файла метаданных среды выполнения Windows (.winmd).  
  
```  
/WINMD[:{NO|ONLY}]  
```  
  
## <a name="remarks"></a>Примечания  
 /WINMD  
 Значение по умолчанию для приложений универсальной платформы Windows. Компоновщик создает двоичный исполняемый файл и файл метаданных winmd.  
  
 /WINMD:NO  
 Компоновщик создает двоичный исполняемый файл, но не в winmd-файл.  
  
 /WINMD:ONLY  
 Компоновщик создает winmd-файл, но не двоичный исполняемый файл.  
  
 По умолчанию имя выходного файла имеет вид `binaryname`.winmd. Чтобы указать другое имя файла, используйте [/WINMDFILE](../../build/reference/winmdfile-specify-winmd-file.md) параметр.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Выберите **компоновщика** папки.  
  
3.  Выберите **метаданных Windows** страницу свойств.  
  
4.  В **создавать метаданные Windows** раскрывающемся списке выберите нужный вариант.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)