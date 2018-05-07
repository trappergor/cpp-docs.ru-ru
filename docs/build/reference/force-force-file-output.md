---
title: -FORCE (назначенный файл вывода) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.ForceLink
- /force
dev_langs:
- C++
helpviewer_keywords:
- FORCE linker option
- file output in linker
- /FORCE linker option
- -FORCE linker option
ms.assetid: b1e9a218-a5eb-4e60-a4a4-65b4be15e5da
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d1daa27ce48590d4a122eafde9f63f7142271610
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="force-force-file-output"></a>/FORCE (Назначенный файл вывода)
```  
/FORCE:[MULTIPLE|UNRESOLVED]  
```  
  
## <a name="remarks"></a>Примечания  
 Параметр/Force предписывает компоновщику создать файл допустимым .exe или DLL даже если на символ существует ссылка, но не определен или умножения определенных.  
  
 Параметр/Force может получать необязательный аргумент:  
  
-   Используйте/FORCE: Multiple для создания выходного файла ли ссылка обнаруживает несколько определений символа.  
  
-   Использовать параметр/FORCE: UNRESOLVED для создания выходного файла ли ссылка будет находить неопределенного символа. / FORCE: НЕРАЗРЕШЕННЫЕ игнорируется, если символ точки входа не распознано.  
  
 / FORCE без аргументов выражает как многократные и оставаться неразрешенным.  
  
 Файл, созданный с помощью этого параметра может не работать должным образом. Компоновщик не компонует инкрементно, если указан параметр/Force.  
  
 Если модуль компилируется с **/CLR**, **/FORCE** образ не создается.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [задание свойств проекта Visual C++](../../ide/working-with-project-properties.md).  
  
2.  Нажмите кнопку **компоновщика** папки.  
  
3.  Выберите страницу свойств **Командная строка** .  
  
4.  Введите параметр в **Дополнительные параметры** поле.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)