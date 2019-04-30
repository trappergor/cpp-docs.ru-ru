---
title: /ALIGN (выравнивание разделов)
ms.date: 12/29/2017
f1_keywords:
- VC.Project.VCLinkerTool.Alignment
- /align
helpviewer_keywords:
- sections, specifying alignment
- ALIGN linker option
- /ALIGN linker option
- -ALIGN linker option
- section alignment
- sections
ms.openlocfilehash: d8d2e6a859c68af473d49dc04b76f0a15056aa56
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62295270"
---
# <a name="align-section-alignment"></a>/ALIGN (выравнивание разделов)

## <a name="syntax"></a>Синтаксис

> **/ ALIGN**[**:**_номер_]

### <a name="arguments"></a>Аргументы

*номер*<br/>
Значение выравнивания в байтах.

## <a name="remarks"></a>Примечания

**/ALIGN** параметр определяет выравнивание каждого раздела в рамках линейного адресного пространства программы. *Номер* аргумент задается в байтах и должен быть степенью двух. Значение по умолчанию составляет 4 КБ (4096). Компоновщик выдаст предупреждение, если выравнивание создается Недопустимое изображение.

Если вы создаете приложение, например драйвером устройства, нет необходимости вносить изменения в выравнивание.

Можно изменить выравнивание определенного раздела в параметре выровнять [/SECTION](section-specify-section-attributes.md) параметр.

Значение выравнивания вами не может быть меньше, чем наибольшее выравнивание разделов.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **компоновщика** > **командной строки** страницу свойств.

1. Введите параметр в **Дополнительные параметры** поле. Выберите **ОК** или **применить** для применения изменений.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[Справочник по компоновщику MSVC](linking.md)<br/>
[Параметры компоновщика MSVC](linker-options.md)
