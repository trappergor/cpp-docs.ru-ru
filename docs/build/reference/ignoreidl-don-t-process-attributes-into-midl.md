---
title: -IGNOREIDL (Don&#39;t атрибуты в MIDL) | Документация Майкрософт
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
ms.openlocfilehash: 9c06e06633e6d0a990c72ebb65a4bd999df45a55
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46406676"
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