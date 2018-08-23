---
title: -MIDL (указание параметров командной строки MIDL) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /midl
- VC.Project.VCLinkerTool.MidlCommandFile
dev_langs:
- C++
helpviewer_keywords:
- -MIDL linker option
- MIDL
- /MIDL linker option
- MIDL linker option
- MIDL, command line options
ms.assetid: 22dc259e-b34c-4ed3-a380-4beb734482c1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7b3f20fddd657d1e5e57caf65ecc8e2c52afbf12
ms.sourcegitcommit: e9ce38decc9f986edab5543de3464b11ebccb123
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2018
ms.locfileid: "42571890"
---
# <a name="midl-specify-midl-command-line-options"></a>/MIDL (Указание параметров командной строки MIDL)
```  
/MIDL:@file  
```  
  
## <a name="remarks"></a>Примечания  
 Здесь:  
  
 `file`  
 Имя файла, содержащего [параметров командной строки MIDL](http://msdn.microsoft.com/library/windows/desktop/aa366839).  
  
## <a name="remarks"></a>Примечания  
 Все параметры для преобразования IDL-файла TLB-файл, которые должны быть заданы в `file`; В командной строке компоновщика нельзя использовать параметры командной строки MIDL. Если/MIDL не указан, компилятор MIDL будет вызываться только имя файла IDL и нет других вариантов.  
  
 Этот файл должен содержать один параметр командной строки MIDL каждой строки.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств проекта Visual C++ параметр](../../ide/working-with-project-properties.md).  
  
2.  Нажмите кнопку **компоновщика** папки.  
  
3.  Нажмите кнопку **внедренные IDL** страницу свойств.  
  
4.  Изменить **MIDL-команды** свойство.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MidlCommandFile%2A>.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)   
 [/ IDLOUT (имен выходным файлам MIDL)](../../build/reference/idlout-name-midl-output-files.md)   
 [/ IGNOREIDL (не процесса атрибуты в MIDL)](../../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)   
 [/ TLBOUT (имя. TLB-файл)](../../build/reference/tlbout-name-dot-tlb-file.md)   
 [Сборка атрибутированной программы](../../windows/building-an-attributed-program.md)