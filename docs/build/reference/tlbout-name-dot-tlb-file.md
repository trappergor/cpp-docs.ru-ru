---
title: -TLBOUT (имя. TLB-файл) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1c44028f834d2b3200b970fdc613d0bf4d4efd29
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45702862"
---
# <a name="tlbout-name-tlb-file"></a>/TLBOUT (задание имени TLB-файла)

```
/TLBOUT:[path\]filename
```

## <a name="arguments"></a>Аргументы

*path*<br/>
Спецификацию абсолютный или относительный путь, для которой должна создаваться TLB-файлу.

*filename*<br/>
Задает имя TLB-файла, созданного компилятором MIDL. Предполагается, что без расширения файла; Укажите *filename*TLB-файл, если вы хотите, чтобы расширением TLB.

## <a name="remarks"></a>Примечания

Параметр/TLBOUT задает имя и расширение TLB-файла.

Компилятор MIDL вызывается компоновщиком Visual C++ при связывании проектов, содержащих [модуль](../../windows/module-cpp.md) атрибута.

Если/TLBOUT не указан, TLB-файлу, получите его имя из [/IDLOUT](../../build/reference/idlout-name-midl-output-files.md) *filename*. Если/IDLOUT не указан, TLB-файл будет называться vc70.tlb.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств проекта Visual C++ параметр](../../ide/working-with-project-properties.md).

1. Нажмите кнопку **компоновщика** папки.

1. Нажмите кнопку **внедренные IDL** страницу свойств.

1. Изменить **библиотеки типов** свойство.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

1. См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TypeLibraryFile%2A>.

## <a name="see-also"></a>См. также

[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)<br/>
[/ IGNOREIDL (не процесса атрибуты в MIDL)](../../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)
[/MIDL (указание параметров командной строки MIDL)](../../build/reference/midl-specify-midl-command-line-options.md)
[сборка Атрибутированной программы](../../windows/building-an-attributed-program.md)