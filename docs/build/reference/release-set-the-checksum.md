---
title: -RELEASE (установить контрольную сумму) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /release
- VC.Project.VCLinkerTool.SetChecksum
dev_langs:
- C++
helpviewer_keywords:
- -RELEASE linker option
- /RELEASE linker option
- checksum setting
- RELEASE linker option
ms.assetid: 93bcadf4-29ac-4824-914b-6997e3751d22
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d360ad7264cb66da140df340bc9d281a329c26c2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32375156"
---
# <a name="release-set-the-checksum"></a>/RELEASE (установить контрольную сумму)
```  
/RELEASE  
```  
  
## <a name="remarks"></a>Примечания  
 Параметр/Release задает контрольную сумму в заголовке файла .exe.  
  
 Операционная система запрашивает контрольную сумму для драйверов устройств. Установите контрольную сумму для предварительных версий драйверов устройств для обеспечения совместимости с будущими операционными системами.  
  
 Параметр/Release имеет значение по умолчанию при [указан](../../build/reference/subsystem-specify-subsystem.md) параметра.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [задание свойств проекта Visual C++](../../ide/working-with-project-properties.md).  
  
2.  Нажмите кнопку **компоновщика** папки.  
  
3.  Нажмите кнопку **Дополнительно** страницу свойств.  
  
4.  Изменить **установить контрольную сумму** свойство.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SetChecksum%2A>.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)