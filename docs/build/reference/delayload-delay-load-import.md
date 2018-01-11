---
title: "-DELAYLOAD (загрузка импорта с задержкой) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /delayload
- VC.Project.VCLinkerTool.DelayLoadDLLS
dev_langs: C++
helpviewer_keywords:
- DELAYLOAD linker option
- -DELAYLOAD linker option
- /DELAYLOAD linker option
- delayed loading of DLLs, /DELAYLOAD option
ms.assetid: 39ea0f1e-5c01-450f-9c75-2d9761ff9b28
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4fd524e72125408c6a88bea83272e18a7ef9b78d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="delayload-delay-load-import"></a>/DELAYLOAD (загрузка импорта с задержкой)
```  
/DELAYLOAD:dllname  
```  
  
## <a name="parameters"></a>Параметры  
 `dllname`  
 Имя DLL-библиотеки, загрузку которой нужно задержать.  
  
## <a name="remarks"></a>Примечания  
 При использовании параметра /DELAYLOAD DLL-библиотека, указанная с помощью `dllname`, загружается только при первом вызове функции этой DLL-библиотеки программой. Дополнительные сведения см. в разделе [поддержка компоновщика для Delay-Loaded DLLs](../../build/reference/linker-support-for-delay-loaded-dlls.md). Можно использовать этот параметр сколько угодно раз, указывая сколько угодно DLL-библиотек. При компоновке программы нужно использовать Delayimp.lib. Также можно использовать собственную вспомогательную функцию загрузки с задержкой.  
  
 [/DELAY](../../build/reference/delay-delay-load-import-settings.md) указывает настройки привязки и загрузки для каждой библиотеки DLL, загружаемых с задержкой.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  В **компоновщика** выберите **ввода** страницу свойств.  
  
3.  Изменить **Отложенно загружаемые DLL** свойство.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.DelayLoadDLLs%2A>.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)