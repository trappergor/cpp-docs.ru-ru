---
title: -IDLOUT (имен выходным файлам MIDL) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /idlout
- VC.Project.VCLinkerTool.MergedIDLBaseFileName
dev_langs:
- C++
helpviewer_keywords:
- MIDL, output file names
- .idl files, path
- MIDL
- /IDLOUT linker option
- IDL files, path
- -IDLOUT linker option
- IDLOUT linker option
ms.assetid: 10d00a6a-85b4-4de1-8732-e422c6931509
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d7eeb7af3d19a57b6948f867df87b8d04d0397b0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32376066"
---
# <a name="idlout-name-midl-output-files"></a>/IDLOUT (присвоение имен выходным файлам MIDL)
```  
/IDLOUT:[path\]filename  
```  
  
## <a name="parameters"></a>Параметры  
 *path*  
 Спецификация абсолютный или относительный путь. Указание пути, влияют на расположение IDL-файл; все остальные файлы размещаются в каталоге проекта.  
  
 *filename*  
 Указывает имя IDL-файл, созданный компилятором MIDL. Предполагается без расширения файла. Укажите *filename*.idl, если требуется, чтобы расширение .idl.  
  
## <a name="remarks"></a>Примечания  
 Параметр/IDLOUT задает имя и расширение IDL-файла.  
  
 Компилятор MIDL вызывается компоновщиком Visual C++ при компоновке проектов, имеющих [модуль](../../windows/module-cpp.md) атрибута.  
  
 / IDLOUT задает также имена файлов других выходных файлов, связанные с компилятором MIDL:  
  
-   *Имя файла*TLB-файл  
  
-   *Имя файла*_p.c  
  
-   *Имя файла*_i.c  
  
-   *Имя файла*.h  
  
 *Имя файла* — параметр, который передается/IDLOUT. Если [/TLBOUT](../../build/reference/tlbout-name-dot-tlb-file.md) указан, TLB-файла получат его имя из/TLBOUT *filename*.  
  
 При указании/IDLOUT ни/TLBOUT, компоновщик создаст vc70.tlb, vc70.idl, vc70_p.c, vc70_i.c и vc70.h.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [задание свойств проекта Visual C++](../../ide/working-with-project-properties.md).  
  
2.  Нажмите кнопку **компоновщика** папки.  
  
3.  Нажмите кнопку **внедренный IDL** страницу свойств.  
  
4.  Изменить **слияния имя файла IDL базы** свойство.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MergedIDLBaseFileName%2A>.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)   
 [/ IGNOREIDL (не преобразовывать атрибуты в MIDL)](../../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)   
 [/ MIDL (указание параметров командной строки MIDL)](../../build/reference/midl-specify-midl-command-line-options.md)   
 [Сборка атрибутированной программы](../../windows/building-an-attributed-program.md)