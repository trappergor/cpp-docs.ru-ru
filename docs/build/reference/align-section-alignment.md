---
title: / ALIGN (выравнивание разделов) | Документация Майкрософт
ms.custom: ''
ms.date: 12/29/2017
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.Alignment
- /align
dev_langs:
- C++
helpviewer_keywords:
- sections, specifying alignment
- ALIGN linker option
- /ALIGN linker option
- -ALIGN linker option
- section alignment
- sections
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cb92d4b16be7903004831ffb25e2891f498a8989
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45718254"
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

Можно изменить выравнивание определенного раздела в параметре выровнять [/SECTION](../../build/reference/section-specify-section-attributes.md) параметр.

Значение выравнивания вами не может быть меньше, чем наибольшее выравнивание разделов.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств проекта Visual C++ параметр](../../ide/working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **компоновщика** > **командной строки** страницу свойств.

1. Введите параметр в **Дополнительные параметры** поле. Выберите **ОК** или **применить** для применения изменений.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)
