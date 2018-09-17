---
title: -WX (обработка предупреждений компоновщика как ошибки) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /WX
dev_langs:
- C++
helpviewer_keywords:
- /WX linker option
- -WX linker option
- WX linker option
ms.assetid: e4ba97c7-93f7-43ae-a4bb-d866790926c9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 91f73af0c270be4452a4b556d2cb77c0d55bed33
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45722596"
---
# <a name="wx-treat-linker-warnings-as-errors"></a>/WX (Обрабатывать предупреждения компоновщика как ошибки)

```
/WX[:NO]
```

## <a name="remarks"></a>Примечания

Параметр /WX выходной файл не будет создан, если компоновщик создает предупреждение.

Это похоже на **/WX** компилятором (см. в разделе [/w, / W0, / W1, / w2, / w3, / W4, / W1, / w2, / w3, / W4, / Wall, / WD, / we, / WO, / wv, /WX (уровень предупреждений)](../../build/reference/compiler-option-warning-level.md) Дополнительные сведения). Однако, если задать **/WX** для компиляции не означает, что **/WX** также вступят в силу на этапе компоновки; необходимо явно указать **/WX** для каждого средства.

По умолчанию **/WX** не действует. Чтобы обрабатывать предупреждения компоновщика как ошибки, укажите **/WX**. **/WX:no** совпадает со значением не указывая **/WX**.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств проекта Visual C++ параметр](../../ide/working-with-project-properties.md).

1. Нажмите кнопку **компоновщика** папки.

1. Выберите страницу свойств **Командная строка** .

1. Введите параметр в **Дополнительные параметры** поле.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

1. См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)