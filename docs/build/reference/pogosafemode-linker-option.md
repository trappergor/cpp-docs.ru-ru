---
title: / POGOSAFEMODE (PGO запуска в безопасном режиме потока) | Документы Microsoft
ms.custom: ''
ms.date: 03/14/2018
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
f1_keywords:
- POGOSAFEMODE
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 81392c67b47a0fa90c057ee4295667a054e34498
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32377337"
---
# <a name="pogosafemode-run-pgo-in-thread-safe-mode"></a>/ POGOSAFEMODE (PGO запуска в безопасном режиме потока)

**Параметр /POGOSAFEMODE является устаревшим, начиная с Visual Studio 2015**. Используйте [/genprofile: ТОЧНОЕ](genprofile-fastgenprofile-generate-profiling-instrumented-build.md) и **/GENPROFILE:NOEXACT** вместо этого. **/POGOSAFEMODE** компоновщика указывает, инструментированной сборки создается для использования режима поточно ориентированного для профиля система отслеживания измененных данных во время профильной оптимизации (PGO) обучения выполняется.

## <a name="syntax"></a>Синтаксис

> **/ POGOSAFEMODE**

## <a name="remarks"></a>Примечания

Профильная оптимизация (PGO) имеет два возможных режима во время фазы профилирования: *быстрый режим* и *безопасный режим*. При профилировании в быстром режиме для увеличения счетчиков данных используется приращение. Инструкция приращение выполняется быстрее, но не является потокобезопасной. При профилировании в безопасном режиме для увеличения счетчиков данных используется заблокированную инкремента. Эта инструкция имеет ту же функциональность, как инструкции приращения и потоками, но работает медленнее.

**/POGOSAFEMODE** параметр устанавливает инструментированную сборку в безопасном режиме. Этот параметр может быть только используется, когда устаревшие [/LTCG: PGINSTRUMENT](ltcg-link-time-code-generation.md) указывается во время фазы компоновщика инструментирования профильной Оптимизации.

По умолчанию профилирование вероятностного Оптимизатора работает в быстром режиме. **/ POGOSAFEMODE** — требуется, только если вы хотите использовать безопасный режим.

Чтобы выполнить профилирование вероятностного Оптимизатора в безопасном режиме, необходимо использовать **/genprofile: ТОЧНОЕ** (предпочтительно), или использовать переменную среды [PogoSafeMode](environment-variables-for-profile-guided-optimizations.md) или параметр компоновщика **/POGOSAFEMODE**, в зависимости от системы. Если вы выполняете профилирование на x64 компьютера, необходимо использовать параметр компоновщика. Если вы выполняете профилирование на x86 компьютера, можно использовать параметр компоновщика или задать для переменной среды любое значение перед началом процесса инструментирования профильной Оптимизации.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [задание свойств проекта Visual C++](../../ide/working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **компоновщика** > **оптимизации** страницу свойств.

1. В **кода во время компоновки** свойства, выберите **Ведомая профилем оптимизация - инструмент (/ LTCG: PGINSTRUMENT)**.

1. Выберите **свойства конфигурации** > **компоновщика** > **командной строки** страницу свойств.

1. Введите **/POGOSAFEMODE** параметр в **Дополнительные параметры** поле. Выберите **ОК** для сохранения изменений.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[/ GENPROFILE и/fastgenprofile](genprofile-fastgenprofile-generate-profiling-instrumented-build.md)<br/>
[/LTCG](ltcg-link-time-code-generation.md)<br/>
[Профильная оптимизация](../../build/reference/profile-guided-optimizations.md)<br/>
[Переменные среды для профильной оптимизации](../../build/reference/environment-variables-for-profile-guided-optimizations.md)<br/>
