---
title: -MAP (Создание файла сопоставления) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /map
- VC.Project.VCLinkerTool.MapFileName
- VC.Project.VCLinkerTool.GenerateMapFile
dev_langs:
- C++
helpviewer_keywords:
- mapfiles, creating linker
- generate mapfile linker option
- mapfile linker option
- mapfiles, information about program being linked
- MAP linker option
- -MAP linker option
- mapfiles, specifying file name
- /MAP linker option
ms.assetid: 9ccce53d-4e36-43da-87b0-7603ddfdea63
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 10f4b23cf8f1c05fb8bd196dc9a6cd54971b1572
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32374675"
---
# <a name="map-generate-mapfile"></a>/MAP (создание файла сопоставления)
```  
/MAP[:filename]  
```  
  
## <a name="remarks"></a>Примечания  
 Здесь:  
  
 *filename*  
 Указанное пользователем имя файла сопоставления. Он заменяет имя по умолчанию.  
  
## <a name="remarks"></a>Примечания  
 Параметр/MAP предписывает компоновщику Создание файла сопоставления.  
  
 По умолчанию компоновщик дает файлу сопоставления базовое имя программы и расширение MAP. Необязательный *filename* позволяет переопределить имя по умолчанию для файла сопоставления.  
  
 Файл сопоставления представляет текстовый файл, содержащий следующие сведения о компонующейся программе:  
  
-   Имя модуля, который является базовым именем файла  
  
-   Отметка времени из заголовка файла программы (не из файловой системы)  
  
-   Список групп в программе, имеющий начальный адрес для каждой группы (как *раздел*:*смещение*), длина имени группы и класса  
  
-   Список открытых символов с каждым адресом (как *раздел*:*смещение*), символ имени, неструктурированного адреса и OBJ-файл, в котором определен символ  
  
-   Точка входа (как *раздел*:*смещение*)  
  
 [/MAPINFO](../../build/reference/mapinfo-include-information-in-mapfile.md) указывает Дополнительные сведения, которые будут включены в файл сопоставления.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [задание свойств проекта Visual C++](../../ide/working-with-project-properties.md).  
  
2.  Нажмите кнопку **компоновщика** папки.  
  
3.  Нажмите кнопку **отладки** страницу свойств.  
  
4.  Изменить **Создание файла сопоставления** свойство.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом  
  
1.  См. разделы <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.GenerateMapFile%2A> и <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MapFileName%2A>.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)