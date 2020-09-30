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
ms.openlocfilehash: 62913eaadd0f0a88f05ce347a6778062a1e66f17
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91509343"
---
# <a name="tlbout-name-tlb-file"></a>/TLBOUT (задание имени TLB-файла)

```
/TLBOUT:[path\]filename
```

## <a name="arguments"></a>Аргументы

*путь*<br/>
Абсолютная или относительная спецификация пути для создания TLB.

*filename*<br/>
Указывает имя файла TLB, созданного компилятором MIDL. Расширение файла не предполагается. Укажите *filename*. tlb, если требуется расширение TLB.

## <a name="remarks"></a>Remarks

Параметр/TLBOUT задает имя и расширение файла TLB.

Компилятор MIDL вызывается компоновщиком КОМПИЛЯТОРОМ MSVC при связывании проектов, имеющих атрибут [module](../../windows/attributes/module-cpp.md) .

Если/TLBOUT не указан, TLB-файл получит имя из [/IDLOUT](idlout-name-midl-output-files.md) *filename*. Если/IDLOUT не указан, TLB-файл будет называться vc70. tlb.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Выберите папку **компоновщика**.

1. Щелкните страницу свойств **встроенного IDL** .

1. Измените свойство **библиотеки типов** .

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

1. См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TypeLibraryFile%2A>.

## <a name="see-also"></a>См. также раздел

[Справочник по компоновщику MSVC](linking.md)<br/>
[Параметры компоновщика MSVC](linker-options.md)<br/>
[/IGNOREIDL (не обрабатывать атрибуты в MIDL)](ignoreidl-don-t-process-attributes-into-midl.md)<br/>
[/MIDL (указание параметров командной строки MIDL)](midl-specify-midl-command-line-options.md)<br/>
[Сборка атрибутированной программы](../../windows/attributes/cpp-attributes-com-net.md)
