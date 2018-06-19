---
title: -IGNOREIDL (Дон&#39;t процесса атрибуты в MIDL) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.IgnoreEmbeddedIDL
- /ignoreidl
dev_langs:
- C++
helpviewer_keywords:
- IGNOREIDL linker option
- -IGNOREIDL linker option
- /IGNOREIDL linker option
ms.assetid: 29514098-6a1c-4317-af2f-1dc268972780
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 14d32be32f019e55f8bad9cc01199d8dc6ae6301
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32373456"
---
# <a name="ignoreidl-don39t-process-attributes-into-midl"></a>/ IGNOREIDL (Дон&#39;t процесса атрибуты в MIDL)
```  
/IGNOREIDL  
```  
  
## <a name="remarks"></a>Примечания  
 Параметр/IGNOREIDL определяет любые [атрибуты IDL](../../windows/idl-attributes.md) в исходном коде не должны обрабатываться в IDL-файл.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [задание свойств проекта Visual C++](../../ide/working-with-project-properties.md).  
  
2.  Нажмите кнопку **компоновщика** папки.  
  
3.  Нажмите кнопку **внедренный IDL** страницу свойств.  
  
4.  Изменить **Игнорировать внедренные IDL** свойство.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreEmbeddedIDL%2A>.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)   
 [/ IDLOUT (имен выходным файлам MIDL)](../../build/reference/idlout-name-midl-output-files.md)   
 [/ TLBOUT (имя. TLB-файл)](../../build/reference/tlbout-name-dot-tlb-file.md)   
 [/ MIDL (указание параметров командной строки MIDL)](../../build/reference/midl-specify-midl-command-line-options.md)   
 [Сборка атрибутированной программы](../../windows/building-an-attributed-program.md)