---
title: /QIntel-jcc-erratum
description: Описывает параметр/Кинтел-ЖКК-ерратум компилятора Microsoft C/C++ (КОМПИЛЯТОРОМ MSVC).
ms.date: 01/07/2020
f1_keywords:
- QIntel-jcc-erratum
helpviewer_keywords:
- /QIntel-jcc-erratum
- -QIntel-jcc-erratum
ms.openlocfilehash: c66dd4bb25647ce193bce4db5dc4ebb1268277c0
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92921377"
---
# <a name="qintel-jcc-erratum"></a>/QIntel-jcc-erratum

::: moniker range="<=msvc-150"

Параметр **/кинтел-ЖКК-ерратум** доступен в Visual Studio 2019 версии 16,5 и более поздних версиях.

::: moniker-end

::: moniker range=">=msvc-160"

Указывает, что компилятор создает инструкции по снижению производительности, вызванной обновлением микрокода с помощью условного кода Intel (ЖКК), в некоторых процессорах Intel.

## <a name="syntax"></a>Синтаксис

> **/QIntel-jcc-erratum**

## <a name="remarks"></a>Remarks

В разделе **/кинтел-ЖКК-ерратум** компилятор обнаруживает инструкции по переходу и использованию предохранителя макроса, которые пересекаются или заканчиваются на границе 32 байта. Эти инструкции выводятся в соответствие с границей. Это изменение снижает влияние обновлений микрокода на производительность, предотвращающих дефекты ЖКК в некоторых процессорах Intel. Дополнительные сведения об ошибках см. в разделе [Устранение ошибок условного кода для перехода](https://www.intel.com/content/dam/support/us/en/documents/processors/mitigations-jump-conditional-code-erratum.pdf) на веб-сайт Intel.

Параметр **/кинтел-ЖКК-ерратум** доступен в Visual Studio 2019 версии 16,5 и более поздних версиях. Этот параметр доступен только в компиляторах, предназначенных для x86 и x64. Параметр недоступен в компиляторах, предназначенных для процессоров ARM.

Параметр **/кинтел-ЖКК-ерратум** отключен по умолчанию и работает только в оптимизированных сборках. Этот параметр может увеличить размер кода.

**/Кинтел-ЖКК-ерратум** несовместим с [/CLR](clr-common-language-runtime-compilation.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Выберите страницу свойств **Свойства "** > Создание кода **C/C++** " > **Code Generation** .

1. Выберите значение для свойства **включить устранение дефектов Intel ЖКК** . Чтобы применить изменение, нажмите кнопку **ОК** .

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также статью

[Параметры/q (низкоуровневые операции)](q-options-low-level-operations.md)\
[Параметры компилятора КОМПИЛЯТОРОМ MSVC](compiler-options.md)\
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)

::: moniker-end
