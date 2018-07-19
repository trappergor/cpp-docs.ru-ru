---
title: / Параметр USEPROFILE (использование профильной Оптимизации данных с LTCG) | Документы Microsoft
ms.custom: ''
ms.date: 03/14/2018
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
f1_keywords:
- USEPROFILE
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 156a571eaa3db31b8c5345f1550346503651665d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32377997"
---
# <a name="useprofile-run-pgo-in-thread-safe-mode"></a>/ Параметр USEPROFILE (PGO запуска в безопасном режиме потока)

Этот параметр компоновщика вместе с [/LTCG (Создание кода во время компоновки](ltcg-link-time-code-generation.md) указывает компоновщику построения с использованием данных обучения профильной оптимизации (PGO).

## <a name="syntax"></a>Синтаксис

> **/ Параметр USEPROFILE**[**:**{**АГРЕССИВНАЯ**|**PGD =**_filename_}]

### <a name="arguments"></a>Аргументы

**АГРЕССИВНЫЙ**<br/>
Этот необязательный аргумент указывает, оптимизации скорости агрессивной должны использоваться во время создания оптимизированного кода.

**PGD**=*имя файла*<br/>
Указывает имя базового файла для PGD-файла. По умолчанию компоновщик использует имя базового исполняемого файла с расширением PGD.

## <a name="remarks"></a>Примечания

**Параметром/useprofile** компоновщика используется совместно с **/LTCG** для создания или обновления оптимизированные сборки, на основе данных обучения профильной Оптимизации. Это эквивалентно использованию из устаревших **/LTCG: PGUPDATE** и **/LTCG: PGOPTIMIZE** параметры.

Необязательный **АГРЕССИВНАЯ** аргумент отключает размерные эвристику для оптимизации быстродействия. Это может привести к оптимизации, которые значительно увеличить размер исполняемого файла и не может увеличить скорость результирующее. Следует профилирования и сравнить результаты с помощью и не **АГРЕССИВНАЯ**. Этот аргумент должен быть задан явно; Эта возможность отключена по умолчанию.

**PGD** аргумент указывает необязательное имя PGD-файла обучающих данных для использования, так же, как в [/genprofile или/fastgenprofile](genprofile-fastgenprofile-generate-profiling-instrumented-build.md). Это эквивалентно использованию из устаревших **/PGD** переключения. По умолчанию или если ни один *filename* указано, PGD-файла с тем же базовым именем, что и исполняемый файл используется.

**Параметром/useprofile** параметра компоновщика в Visual Studio 2015.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [задание свойств проекта Visual C++](../../ide/working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **компоновщика** > **оптимизации** страницу свойств.

1. В **кода во время компоновки** свойства, выберите **используйте создание кода во время компоновки (/ LTCG)**.

1. Выберите **свойства конфигурации** > **компоновщика** > **командной строки** страницу свойств.

1. Введите **параметром/useprofile** и необязательные аргументы в **Дополнительные параметры** поле. Выберите **ОК** для сохранения изменений.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[/ GENPROFILE и/fastgenprofile](genprofile-fastgenprofile-generate-profiling-instrumented-build.md)<br/>
[/LTCG](ltcg-link-time-code-generation.md)<br/>
[Профильная оптимизация](../../build/reference/profile-guided-optimizations.md)<br/>
[Переменные среды для профильной оптимизации](../../build/reference/environment-variables-for-profile-guided-optimizations.md)<br/>
