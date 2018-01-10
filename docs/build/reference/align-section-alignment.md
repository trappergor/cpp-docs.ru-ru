---
title: "/ ALIGN (выравнивание разделов) | Документы Microsoft"
ms.custom: 
ms.date: 12/29/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.Alignment
- /align
dev_langs: C++
helpviewer_keywords:
- sections, specifying alignment
- ALIGN linker option
- /ALIGN linker option
- -ALIGN linker option
- section alignment
- sections
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4ca4572e84c7ad32be2d03a312f7bb7d8a3f3f29
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/03/2018
---
# <a name="align-section-alignment"></a>/ALIGN (выравнивание разделов)

## <a name="syntax"></a>Синтаксис

> **/ ALIGN**[**:**_номер_]

### <a name="arguments"></a>Аргументы

*номер*  
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
