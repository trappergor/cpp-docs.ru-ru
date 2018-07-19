---
title: -WINMD (создавать метаданные Windows) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.GenerateWindowsMetadata
dev_langs:
- C++
ms.assetid: bcfb4901-411e-4c9e-9f78-23028b6e5fcc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0d3e628713c8228675db3b34e70d670c88152462
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32376183"
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
  
 / WINMD: ТОЛЬКО  
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