---
title: "-TLBOUT (имя. TLB-файл) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.TypeLibraryFile
- /tlbout
dev_langs:
- C++
helpviewer_keywords:
- tlb files, renaming
- TLBOUT linker option
- /TLBOUT linker option
- .tlb files, renaming
- -TLBOUT linker option
ms.assetid: 0df6d078-2e48-46c9-a1a5-02674d85dce8
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2c898121a4ac29cc05022504ebfe33949b44eca7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="tlbout-name-tlb-file"></a>/TLBOUT (задание имени TLB-файла)
```  
/TLBOUT:[path\]filename  
```  
  
## <a name="remarks"></a>Примечания  
 Здесь:  
  
 *path*  
 Спецификация абсолютный или относительный путь, для которой должен быть создан TLB-файл.  
  
 *filename*  
 Указывает имя файла TLB-файл, созданный компилятором MIDL. Предполагается без расширения файла. Укажите *filename*TLB-файл, если требуется расширением TLB.  
  
## <a name="remarks"></a>Примечания  
 Параметр/TLBOUT задает имя и расширение TLB-файла.  
  
 Компилятор MIDL вызывается компоновщиком Visual C++ при компоновке проектов, имеющих [модуль](../../windows/module-cpp.md) атрибута.  
  
 Если/TLBOUT не указан, TLB-файл получит его имя из [/IDLOUT](../../build/reference/idlout-name-midl-output-files.md) *filename*. Если/IDLOUT не указан, TLB-файл будет называться vc70.tlb.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [задание свойств проекта Visual C++](../../ide/working-with-project-properties.md).  
  
2.  Нажмите кнопку **компоновщика** папки.  
  
3.  Нажмите кнопку **внедренный IDL** страницу свойств.  
  
4.  Изменить **библиотеки типов** свойство.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом  
  
1.  См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TypeLibraryFile%2A>.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)   
 [/ IGNOREIDL (не преобразовывать атрибуты в MIDL)](../../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)   
 [/ MIDL (указание параметров командной строки MIDL)](../../build/reference/midl-specify-midl-command-line-options.md)   
 [Сборка атрибутированной программы](../../windows/building-an-attributed-program.md)