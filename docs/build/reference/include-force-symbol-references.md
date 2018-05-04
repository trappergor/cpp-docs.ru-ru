---
title: -INCLUDE (Принудительная ссылка на символ) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /include
- VC.Project.VCLinkerTool.ForceSymbolReferences
dev_langs:
- C++
helpviewer_keywords:
- INCLUDE linker option
- force symbol references linker option
- symbol references linker force
- /INCLUDE linker option
- symbols, add to symbol table
- -INCLUDE linker option
ms.assetid: 4a039677-360a-480f-bd0b-448e239b449c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cfe65344e41b98841c3a4e7bca72b762197510b8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="include-force-symbol-references"></a>/INCLUDE (принудительные ссылки на символы)
```  
/INCLUDE:symbol  
```  
  
## <a name="remarks"></a>Примечания  
 Здесь:  
  
 `symbol`  
 Указывает символ для добавления в таблицу символов.  
  
## <a name="remarks"></a>Примечания  
 Параметр/include предписывает компоновщику добавить заданный символ в таблицу символов.  
  
 Чтобы указать несколько символов, введите запятую (,), точка с запятой (;) или пробел между имена символов. В командной строке необходимо указать/include:`symbol` один раз для каждого символа.  
  
 Компоновщик разрешает `symbol` , добавляя объект, содержащий определения символа в программу. Эта возможность полезна для включения объект библиотеки, в противном случае не будут связаны в программу.  
  
 Указание символ этот параметр переопределяет удаление данного символа с [/OPT: ref](../../build/reference/opt-optimizations.md).  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [задание свойств проекта Visual C++](../../ide/working-with-project-properties.md).  
  
2.  Нажмите кнопку **компоновщика** папки.  
  
3.  Нажмите кнопку **ввода** страницу свойств.  
  
4.  Изменить **принудительные ссылки на символы** свойство.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ForceSymbolReferences%2A>.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)