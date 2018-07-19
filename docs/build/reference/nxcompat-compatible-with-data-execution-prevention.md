---
title: / NXCOMPAT (совместимо с предотвращением исполнения данных) | Документы Microsoft
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
ms.openlocfilehash: bb4f8a91545a196bc92fdc0ec44e89a7d5680185
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32374808"
---
# <a name="nxcompat-compatible-with-data-execution-prevention"></a>/NXCOMPAT (совместимо с предотвращением исполнения данных (DEP))

Указывает, что исполняемый файл является совместимую с функцией предотвращения исполнения данных Windows.

## <a name="syntax"></a>Синтаксис

> **/ NXCOMPAT**[**: НЕТ**]

## <a name="remarks"></a>Примечания

По умолчанию **/NXCOMPAT** включен.

**: No** можно использовать для явного указания исполняемый файл как несовместимый с предотвращением исполнения данных.

Дополнительные сведения о Предотвращение выполнения данных см. статьи:

- [Подробное описание функции предотвращения выполнения данных (DEP)](http://go.microsoft.com/fwlink/p/?linkid=157771)

- [Предотвращение выполнения данных](http://go.microsoft.com/fwlink/p/?linkid=157770)

- [Предотвращение выполнения данных (Windows Embedded)](http://go.microsoft.com/fwlink/p/?linkid=157768)

### <a name="to-set-this-linker-option-in-visual-studio"></a>Настройка этого параметра компоновщика в Visual Studio

1. Откройте диалоговое окно **Окна свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **компоновщика** > **командной строки** страницу свойств.

1. Введите параметр в **Дополнительные параметры** поле. Выберите **ОК** или **применить** для применения изменений.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)  
[Параметры компоновщика](../../build/reference/linker-options.md)  
