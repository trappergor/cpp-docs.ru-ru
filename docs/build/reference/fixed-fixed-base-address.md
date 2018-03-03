---
title: "-FIXED (фиксированный базовый адрес) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /fixed
- VC.Project.VCLinkerTool.FixedBaseAddress
dev_langs:
- C++
helpviewer_keywords:
- preferred base address for loading program
- /FIXED linker option
- -FIXED linker option
- FIXED linker option
ms.assetid: 929bba5e-b7d8-40ed-943e-056aa3710fc5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 201a0357d182713c473fd3e259e4e9c2a71abf4e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="fixed-fixed-base-address"></a>/FIXED (фиксированный базовый адрес)
```  
/FIXED[:NO]  
```  
  
## <a name="remarks"></a>Примечания  
 Указывает операционной системе, чтобы загрузить программу только по ее предпочтительному базовому адресу. Если предпочтительный базовый адрес недоступен, операционная система не загрузить файл. Дополнительные сведения см. в разделе [Параметр /Base (базовый адрес)](../../build/reference/base-base-address.md).  
  
 / Fixed: No является значением по умолчанию для библиотеки DLL, а параметр/FIXED имеет значение по умолчанию для любого другого типа проекта.  
  
 Если указан параметр/fixed, связь не создает раздел переадресации в программе. Во время выполнения Если операционная система не может загрузить программу по указанному адресу, он выдает сообщение об ошибке и не загрузить программу.  
  
 Укажите компоновщике для создания секции перемещения в программе.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Выберите **компоновщика** папки.  
  
3.  Выберите **командной строки** страницу свойств.  
  
4.  Введите имя параметра и задав в **Дополнительные параметры** поле.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)