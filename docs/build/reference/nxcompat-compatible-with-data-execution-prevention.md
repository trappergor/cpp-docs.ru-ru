---
title: / NXCOMPAT (совместимо с предотвращением выполнения данных) | Документация Майкрософт
ms.custom: ''
ms.date: 12/29/2017
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /NXCOMPAT
dev_langs:
- C++
helpviewer_keywords:
- /NXCOMPAT linker option
- -NXCOMPAT linker option
- NXCOMPAT linker option
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 52cf47335c1bed55ca38d508789d65902b335f0f
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45707633"
---
# <a name="nxcompat-compatible-with-data-execution-prevention"></a>/NXCOMPAT (совместимо с предотвращением исполнения данных (DEP))

Указывает, что исполняемый файл совместим с функцией предотвращения исполнения данных Windows.

## <a name="syntax"></a>Синтаксис

> **/ NXCOMPAT**[**: НЕТ**]

## <a name="remarks"></a>Примечания

По умолчанию **/NXCOMPAT** включен.

**: No** можно использовать для явного указания исполняемый файл как несовместимые с предотвращением выполнения данных.

Дополнительные сведения о Предотвращение выполнения данных см. в статьях:

- [Подробное описание функции предотвращения выполнения данных (DEP)](https://support.microsoft.com/en-us/help/875352/a-detailed-description-of-the-data-execution-prevention-dep-feature-in)

- [Предотвращение выполнения данных](/windows/desktop/Memory/data-execution-prevention)

- [Предотвращение выполнения данных (Windows Embedded)](/previous-versions/windows/embedded/ms913190\(v=winembedded.5\))

### <a name="to-set-this-linker-option-in-visual-studio"></a>Настройка этого параметра компоновщика в Visual Studio

1. Откройте диалоговое окно **Окна свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **компоновщика** > **командной строки** страницу свойств.

1. Введите параметр в **Дополнительные параметры** поле. Выберите **ОК** или **применить** для применения изменений.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)
