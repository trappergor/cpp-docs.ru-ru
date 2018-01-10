---
title: "-WINMD (создавать метаданные Windows) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VC.Project.VCLinkerTool.GenerateWindowsMetadata
dev_langs: C++
ms.assetid: bcfb4901-411e-4c9e-9f78-23028b6e5fcc
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 903ab6875457aa8c069c47a2be7f8ff1f5c884a9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="winmd-generate-windows-metadata"></a>/WINMD (создавать метаданные Windows)
Включает создание файла метаданных среды выполнения Windows (.winmd).  
  
```  
/WINMD[:{NO|ONLY}]  
```  
  
## <a name="remarks"></a>Примечания  
 /WINMD  
 Значение по умолчанию для [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] приложений. Компоновщик создает двоичный исполняемый файл и файл метаданных winmd.  
  
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