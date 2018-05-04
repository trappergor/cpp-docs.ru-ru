---
title: / ALIGN (выравнивание разделов) | Документы Microsoft
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
ms.openlocfilehash: 543ea30b06f62939f378167d8598c73f66061f46
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="align-section-alignment"></a>/ALIGN (выравнивание разделов)

## <a name="syntax"></a>Синтаксис

> **/ ALIGN**[**:**_номер_]

### <a name="arguments"></a>Аргументы

*Номер*  
Значение выравнивания в байтах.

## <a name="remarks"></a>Примечания

**/ALIGN** параметр задает выравнивание каждого раздела в линейном адресном пространстве программы. *Номер* аргумент задается в байтах и должен быть степенью двух. Значение по умолчанию — 4 КБ (4096). Компоновщик выдает предупреждение, если при выравнивании создается Недопустимое изображение.

Если вы пишете приложение является драйвером устройства, не следует изменять выравнивание.

Можно изменять выравнивание определенного раздела в параметре выровнять [/SECTION](../../build/reference/section-specify-section-attributes.md) параметр.

Указываемое значение выравнивания не может быть меньше, чем наибольшее выравнивание разделов.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [задание свойств проекта Visual C++](../../ide/working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **компоновщика** > **командной строки** страницу свойств.

1. Введите параметр в **Дополнительные параметры** поле. Выберите **ОК** или **применить** для применения изменений.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)  
[Параметры компоновщика](../../build/reference/linker-options.md)  
