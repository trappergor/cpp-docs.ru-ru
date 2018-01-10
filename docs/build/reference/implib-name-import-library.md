---
title: "-IMPLIB (именование библиотеки импорта) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /implib
- VC.Project.VCLinkerTool.ImportLIbrary
dev_langs: C++
helpviewer_keywords:
- IMPLIB linker option
- /IMPLIB linker option
- -IMPLIB linker option
- import libraries, overriding default name
ms.assetid: fe8f71ab-7055-41b5-8ef8-2b97cfa4a432
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 523fc171aa8df3d0b4c6e09909db7c2c1dc0b833
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="implib-name-import-library"></a>/IMPLIB (именование библиотеки импорта)
  
> / IMPLIB:*имя файла*  
  
## <a name="parameters"></a>Параметры  
  
*filename*  
Пользовательское имя библиотеки импорта. Он заменяет имя по умолчанию.  
  
## <a name="remarks"></a>Примечания  
  
Параметр/IMPLIB переопределяет имя по умолчанию для библиотеки импорта, LINK при построении программы, содержащую экспорты. По умолчанию имя формируется на основе базового имени основного выходного файла и расширение. lib. Программа содержит экспорты, если заданы одно или несколько из следующих:  
  
-   [__Declspec(dllexport)](../../cpp/dllexport-dllimport.md) ключевое слово в исходном коде  
  
-   [ЭКСПОРТЫ](../../build/reference/exports.md) инструкции в DEF-файла  
  
-   [И экспорт](../../build/reference/export-exports-a-function.md) спецификации в команде LINK  
  
 LINK игнорирует/IMPLIB при библиотеку импорта не создается. Если указываются экспортируемые элементы, ссылка не создает библиотеку импорта. При использовании файла экспорта в сборке ССЫЛКУ предполагается, что библиотека импорта уже существует и не создает. Сведения о библиотеках импорта и файлами экспорта. в разделе [Справочник по LIB](../../build/reference/lib-reference.md).  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [задание свойств проекта Visual C++](../../ide/working-with-project-properties.md).  
  
2.  Нажмите кнопку **компоновщика** папки.  
  
3.  Нажмите кнопку **Дополнительно** страницу свойств.  
  
4.  Изменить **библиотека импорта** свойство.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ImportLibrary%2A>.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)