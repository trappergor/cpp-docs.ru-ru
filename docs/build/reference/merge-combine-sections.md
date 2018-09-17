---
title: -MERGE (Слияние разделов) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /merge
- VC.Project.VCLinkerTool.MergeSections
dev_langs:
- C++
helpviewer_keywords:
- sections, combining
- /MERGE linker option
- sections, naming
- sections
- -MERGE linker option
- MERGE linker option
ms.assetid: 10fb20c2-0b3f-4c8d-98a8-f69aedf03d52
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 01768ffcfd647d3e05c0b96647d544e3d68e77d0
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45722674"
---
# <a name="merge-combine-sections"></a>/MERGE (Слияние разделов)

```
/MERGE:from=to
```

## <a name="remarks"></a>Примечания

Параметр/Merge объединяет первую секцию (*из*) со второй (*для*), в результате раздел именования *для*. Например, `/merge:.rdata=.text`.

Если второй раздел не существует, связь переименовывает разделе *из* как *для*.

Параметр/Merge удобен для создания vxd и замены имена разделов, созданный компилятором.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств проекта Visual C++ параметр](../../ide/working-with-project-properties.md).

1. Нажмите кнопку **компоновщика** папки.

1. Нажмите кнопку **Дополнительно** страницу свойств.

1. Изменить **Слияние разделов** свойство.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

1. См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MergeSections%2A>.

## <a name="see-also"></a>См. также

[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)