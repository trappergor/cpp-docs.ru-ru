---
title: "-FORCE (назначенный файл вывода) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.ForceLink
- /force
dev_langs: C++
helpviewer_keywords:
- FORCE linker option
- file output in linker
- /FORCE linker option
- -FORCE linker option
ms.assetid: b1e9a218-a5eb-4e60-a4a4-65b4be15e5da
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8ec19beec52a217df1237de41d0bd81ab447a56d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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