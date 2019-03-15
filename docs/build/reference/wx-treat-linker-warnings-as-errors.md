---
title: /WX (Обрабатывать предупреждения компоновщика как ошибки)
ms.date: 11/04/2016
f1_keywords:
- /WX
helpviewer_keywords:
- /WX linker option
- -WX linker option
- WX linker option
ms.assetid: e4ba97c7-93f7-43ae-a4bb-d866790926c9
ms.openlocfilehash: b4b29ed364d39c5f105dded703b8530c08db35e6
ms.sourcegitcommit: faa42c8a051e746d99dcebe70fd4bbaf3b023ace
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2019
ms.locfileid: "57822097"
---
# <a name="wx-treat-linker-warnings-as-errors"></a>/WX (Обрабатывать предупреждения компоновщика как ошибки)

```
/WX[:NO]
```

## <a name="remarks"></a>Примечания

Параметр /WX выходной файл не будет создан, если компоновщик создает предупреждение.

Это похоже на **/WX** компилятором (см. в разделе [/w, / W0, / W1, / w2, / w3, / W4, / W1, / w2, / w3, / W4, / Wall, / WD, / we, / WO, / wv, /WX (уровень предупреждений)](compiler-option-warning-level.md) Дополнительные сведения). Однако, если задать **/WX** для компиляции не означает, что **/WX** также вступят в силу на этапе компоновки; необходимо явно указать **/WX** для каждого средства.

По умолчанию **/WX** не действует. Чтобы обрабатывать предупреждения компоновщика как ошибки, укажите **/WX**. **/WX:no** совпадает со значением не указывая **/WX**.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. Нажмите кнопку **компоновщика** папки.

1. Выберите страницу свойств **Командная строка** .

1. Введите параметр в **Дополнительные параметры** поле.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

1. См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[Справочник по компоновщику MSVC](linking.md)<br/>
[Параметры компоновщика MSVC](linker-options.md)
