---
title: /кинтел-жкк-ерратум
description: Описывает параметр/Кинтел-ЖКК-ерратум Microsoft CC++ /COMPILER (компилятором MSVC).
ms.date: 01/07/2020
f1_keywords:
- QIntel-jcc-erratum
helpviewer_keywords:
- /QIntel-jcc-erratum
- -QIntel-jcc-erratum
ms.openlocfilehash: f311da04b833b06124c5e6237ea83a31319858ca
ms.sourcegitcommit: a930a9b47bd95599265d6ba83bb87e46ae748949
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2020
ms.locfileid: "76520921"
---
# <a name="qintel-jcc-erratum"></a>/кинтел-жкк-ерратум

::: moniker range="<=vs-2017"

Параметр **/кинтел-ЖКК-ерратум** доступен в Visual Studio 2019 версии 16,5 и более поздних версиях.

::: moniker-end

::: moniker range=">=vs-2019"

Указывает, что компилятор создает инструкции по снижению производительности, вызванной обновлением микрокода с помощью условного кода Intel (ЖКК), в некоторых процессорах Intel.

## <a name="syntax"></a>Синтаксис

> **/кинтел-жкк-ерратум**

## <a name="remarks"></a>Заметки

В разделе **/кинтел-ЖКК-ерратум**компилятор обнаруживает инструкции по переходу и использованию предохранителя макроса, которые пересекаются или заканчиваются на границе 32 байта. Эти инструкции выводятся в соответствие с границей. Это изменение снижает влияние обновлений микрокода на производительность, предотвращающих дефекты ЖКК в некоторых процессорах Intel. Дополнительные сведения об ошибках см. в разделе [Устранение ошибок условного кода для перехода](https://www.intel.com/content/dam/support/us/en/documents/processors/mitigations-jump-conditional-code-erratum.pdf) на веб-сайт Intel.

Параметр **/кинтел-ЖКК-ерратум** доступен в Visual Studio 2019 версии 16,5 и более поздних версиях. Этот параметр доступен только в компиляторах, предназначенных для x86 и x64. Параметр недоступен в компиляторах, предназначенных для процессоров ARM.

Параметр **/кинтел-ЖКК-ерратум** отключен по умолчанию и работает только в оптимизированных сборках. Этот параметр может увеличить размер кода.

**/Кинтел-ЖКК-ерратум** несовместим с [/CLR](clr-common-language-runtime-compilation.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Выберите **Свойства конфигурации** > странице свойств **создания кода** **C++ C/** >.

1. Выберите значение для свойства **включить устранение дефектов Intel ЖКК** . Чтобы применить изменение, нажмите кнопку **ОК**.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также:

[Параметры/q (низкоуровневые операции)](q-options-low-level-operations.md)\
\ [параметров компилятора компилятором MSVC](compiler-options.md)
[Синтаксис командной строки компилятора КОМПИЛЯТОРОМ MSVC](compiler-command-line-syntax.md)

::: moniker-end
