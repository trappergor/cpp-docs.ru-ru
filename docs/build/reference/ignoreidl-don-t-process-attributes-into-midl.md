---
title: / IGNOREIDL (Don&#39;t атрибуты в MIDL)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.IgnoreEmbeddedIDL
- /ignoreidl
helpviewer_keywords:
- IGNOREIDL linker option
- -IGNOREIDL linker option
- /IGNOREIDL linker option
ms.assetid: 29514098-6a1c-4317-af2f-1dc268972780
ms.openlocfilehash: f6c5fcbae52ed695f2d0c389607ac4231f069788
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50534359"
---
# <a name="ignoreidl-don39t-process-attributes-into-midl"></a>/ IGNOREIDL (Don&#39;t атрибуты в MIDL)

```
/IGNOREIDL
```

## <a name="remarks"></a>Примечания

Параметр/IGNOREIDL указывает, что все [атрибуты IDL](../../windows/idl-attributes.md) в исходный код не будут обрабатываться в IDL-файле.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств проекта Visual C++ параметр](../../ide/working-with-project-properties.md).

1. Нажмите кнопку **компоновщика** папки.

1. Нажмите кнопку **внедренные IDL** страницу свойств.

1. Изменить **Игнорировать внедренные IDL** свойство.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreEmbeddedIDL%2A>.

## <a name="see-also"></a>См. также

[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)<br/>
[/IDLOUT (присвоение имен выходным файлам MIDL)](../../build/reference/idlout-name-midl-output-files.md)<br/>
[/TLBOUT (именование файла TLB)](../../build/reference/tlbout-name-dot-tlb-file.md)<br/>
[/MIDL (указание параметров командной строки MIDL)](../../build/reference/midl-specify-midl-command-line-options.md)<br/>
[Сборка атрибутированной программы](../../windows/building-an-attributed-program.md)