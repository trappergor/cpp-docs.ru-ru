---
title: -FIXED (фиксированный базовый адрес) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 08b1193b7cfe58aed45e4feec598a49227eafc87
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32374165"
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