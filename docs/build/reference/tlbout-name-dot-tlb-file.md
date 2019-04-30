---
title: /TLBOUT (задание имени TLB-файла)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.TypeLibraryFile
- /tlbout
helpviewer_keywords:
- tlb files, renaming
- TLBOUT linker option
- /TLBOUT linker option
- .tlb files, renaming
- -TLBOUT linker option
ms.assetid: 0df6d078-2e48-46c9-a1a5-02674d85dce8
ms.openlocfilehash: 4e04514933a521bbf9d927fa6b47bacb87896353
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62317644"
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

Компилятор MIDL вызывается MSVC компоновщиком при связывании проектов, содержащих [модуль](../../windows/module-cpp.md) атрибута.

Если/TLBOUT не указан, TLB-файлу, получите его имя из [/IDLOUT](idlout-name-midl-output-files.md) *filename*. Если/IDLOUT не указан, TLB-файл будет называться vc70.tlb.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. Нажмите кнопку **компоновщика** папки.

1. Нажмите кнопку **внедренные IDL** страницу свойств.

1. Изменить **библиотеки типов** свойство.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

1. См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TypeLibraryFile%2A>.

## <a name="see-also"></a>См. также

[Справочник по компоновщику MSVC](linking.md)<br/>
[Параметры компоновщика MSVC](linker-options.md)<br/>
[/IGNOREIDL (запрет преобразования атрибутов в MIDL)](ignoreidl-don-t-process-attributes-into-midl.md)<br/>
[/MIDL (указание параметров командной строки MIDL)](midl-specify-midl-command-line-options.md)<br/>
[Сборка атрибутированной программы](../../windows/building-an-attributed-program.md)
