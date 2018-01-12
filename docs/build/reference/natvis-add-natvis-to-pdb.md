---
title: "-NATVIS (Добавить Natvis в PDB-ФАЙЛ) | Документы Microsoft"
ms.date: 08/10/2017
ms.tgt_pltfrm: 
ms.technology: cpp-tools
ms.topic: article
f1_keywords:
- /natvis
- VC.Project.VCLinkerTool.ImportLIbrary
dev_langs: C++
helpviewer_keywords:
- NATVIS linker option
- /NATVIS linker option
- -NATVIS linker option
- Add Natvis file to PDB
ms.assetid: 8747fc0c-701a-4796-bb4d-818ab4465cca
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 20715b48413a705aa2338e7e37538171e4141cad
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="natvis-add-natvis-to-pdb"></a>/ NATVIS (Добавить Natvis в PDB-ФАЙЛ)
  
> / NATVIS:*имя файла*  
  
## <a name="parameters"></a>Параметры  
  
*filename*  
Natvis-файл для добавления в PDB-файл. Она внедряет визуализация отладчика в natvis-файл в PDB-ФАЙЛ.  
  
## <a name="remarks"></a>Примечания  
  
Параметр /NATVIS внедряет визуализация отладчика, определенные в файле Natvis *filename* в PDB-файл, созданный с помощью LINK. Это позволяет отладчику отображать визуализации, независимо от natvis-файл. Можно использовать несколько параметров /NATVIS для внедрения более одного файла Natvis в файл PDB.  
  
LINK игнорирует /NATVIS при PDB-файл не создан с помощью [/DEBUG](../../build/reference/debug-generate-debug-info.md) параметр. Сведения на создание и использование natvis-файлов см. в разделе [Создание настраиваемых представлений собственных объектов в отладчике Visual Studio](/visualstudio/debugger/create-custom-views-of-native-objects).  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [задание свойств проекта Visual C++](../../ide/working-with-project-properties.md).  
  
2.  Выберите **командной строки** на странице свойств в **компоновщика** папки.  
  
3.  Добавьте параметр /NATVIS **Дополнительные параметры** текстовое поле.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом  
  
-   Этот параметр не поддерживает программный эквивалент.  
  
## <a name="see-also"></a>См. также  
  
[Создание настраиваемых представлений собственных объектов в отладчике Visual Studio](/visualstudio/debugger/create-custom-views-of-native-objects)  
[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)  
[Параметры компоновщика](../../build/reference/linker-options.md)