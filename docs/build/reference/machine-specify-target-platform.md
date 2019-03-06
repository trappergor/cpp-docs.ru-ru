---
title: Параметр /MACHINE (определение целевой платформы)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.TargetMachine
- /machine
helpviewer_keywords:
- mapfiles, creating linker
- target platform
- -MACHINE linker option
- /MACHINE linker option
- MACHINE linker option
ms.assetid: 8d41bf4b-7e53-4ab9-9085-d852b08d31c2
ms.openlocfilehash: 713cff8a787b6eb97ad5d9bea32b6fd77fa64f17
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57426580"
---
# <a name="machine-specify-target-platform"></a>Параметр /MACHINE (определение целевой платформы)

```
/MACHINE:{ARM|EBC|X64|X86}
```

## <a name="remarks"></a>Примечания

Параметр/Machine определяет целевую платформу программы.

Как правило не нужно указать параметр/Machine. Тип компьютера из OBJ-файлов определяется связь. Тем не менее в некоторых случаях связь не может определить тип компьютера и проблемах [средств компоновщика LNK1113 ошибка](../../error-messages/tool-errors/linker-tools-error-lnk1113.md). Если возникает такая ошибка, укажите/Machine.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств проекта Visual C++ параметр](../../ide/working-with-project-properties.md).

1. Нажмите кнопку **компоновщика** папки.

1. Нажмите кнопку **Дополнительно** страницу свойств.

1. Изменить **целевой машины** свойство.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

1. См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TargetMachine%2A>.

## <a name="see-also"></a>См. также

[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)
