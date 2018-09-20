---
title: -IDLOUT (имен выходным файлам MIDL) | Документация Майкрософт
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
ms.openlocfilehash: 6ef4f8b418edcdb903fa8f807cb5e08d63eaeeed
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46441633"
---
# <a name="idlout-name-midl-output-files"></a>/IDLOUT (присвоение имен выходным файлам MIDL)

```
/IDLOUT:[path\]filename
```

## <a name="parameters"></a>Параметры

*path*<br/>
Спецификацию абсолютный или относительный путь. Указание пути, влияет на расположение IDL-файле; все остальные файлы размещаются в каталоге проекта.

*filename*<br/>
Указывает имя IDL-файл, созданный компилятором MIDL. Предполагается, что без расширения файла; Укажите *filename*.idl, если вы хотите, чтобы расширение .idl.

## <a name="remarks"></a>Примечания

Параметр/IDLOUT задает имя и расширение IDL-файла.

Компилятор MIDL вызывается компоновщиком Visual C++ при связывании проектов, содержащих [модуль](../../windows/module-cpp.md) атрибута.

/ IDLOUT задает также имена других выходных файлов, связанных с компилятором MIDL:

- *Имя файла*.tlb

- *Имя файла*_p.c

- *Имя файла*_i.c

- *Имя файла*.h

*Имя файла* параметр, передаваемый/IDLOUT. Если [/TLBOUT](../../build/reference/tlbout-name-dot-tlb-file.md) указан, TLB-файлу получит его имя из/TLBOUT *filename*.

Если указать/IDLOUT ни/TLBOUT, компоновщик создаст vc70.tlb, vc70.idl, vc70_p.c, vc70_i.c и vc70.h.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств проекта Visual C++ параметр](../../ide/working-with-project-properties.md).

1. Нажмите кнопку **компоновщика** папки.

1. Нажмите кнопку **внедренные IDL** страницу свойств.

1. Изменить **слияния имени файла IDL базы** свойство.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MergedIDLBaseFileName%2A>.

## <a name="see-also"></a>См. также

[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)<br/>
[/IGNOREIDL (запрет преобразования атрибутов в MIDL)](../../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)<br/>
[/MIDL (указание параметров командной строки MIDL)](../../build/reference/midl-specify-midl-command-line-options.md)<br/>
[Сборка атрибутированной программы](../../windows/building-an-attributed-program.md)