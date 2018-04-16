---
title: / PGD (Указание базы данных для профильной оптимизации) | Документы Microsoft
ms.custom: ''
ms.date: 03/14/2018
ms.technology:
- cpp-tools
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.ProfileGuidedDatabase
dev_langs:
- C++
helpviewer_keywords:
- -PGD linker option
- /PGD linker option
ms.assetid: 9f312498-493b-461f-886f-92652257e443
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9947e95e3d6c96d07eb12eb2f2a579e0ea1b3a6a
ms.sourcegitcommit: ee7d74683af7631441c8c7f65ef5ceceaee4a5ee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/22/2018
---
# <a name="pgd-specify-database-for-profile-guided-optimizations"></a>/PGD (указание базы данных для профильной оптимизации)

**Параметр/PGD является устаревшим.** Начиная с Visual Studio 2015 предпочитают [/genprofile или/fastgenprofile](genprofile-fastgenprofile-generate-profiling-instrumented-build.md) вместо параметров компоновщика. Этот параметр используется для указания имени PGD-файл, используемый процессом профильной оптимизации.

## <a name="syntax"></a>Синтаксис

> **/PGD:**_filename_

## <a name="argument"></a>Аргумент

*filename*<br/>
Указывает имя PGD-файла, который используется для хранения сведений о выполняемой программы.

## <a name="remarks"></a>Примечания

При использовании устаревших [/LTCG: PGINSTRUMENT](../../build/reference/ltcg-link-time-code-generation.md) , используйте **/PGD** для указания нестандартным именем или расположением PGD-файла. Если вы не укажете **/PGD**, базовое имя файла .pgd совпадает имя выходного файла (.exe или .dll) базового и создается в том же каталоге, из которого был вызван по ссылке.

При использовании устаревших **/LTCG: PGOPTIMIZE** , используйте **/PGD** параметр, чтобы указать имя PGD-файл, используемый для создания оптимизированного образа. *Filename* аргумент должен соответствовать *filename* заданы для **/LTCG: PGINSTRUMENT**.

Дополнительные сведения см. в разделе [профильной оптимизации](../../build/reference/profile-guided-optimizations.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [задание свойств проекта Visual C++](../../ide/working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **компоновщика** > **оптимизации** страницу свойств.

1. Изменить **база данных профиля** свойство. Выберите **ОК** для сохранения изменений.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

1. См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ProfileGuidedDatabase%2A>.

## <a name="see-also"></a>См. также

[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)<br/>
