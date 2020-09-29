---
title: /analyze (анализ кода)
description: Синтаксис и использование параметра/Analyze компилятора Microsoft C++.
ms.date: 07/27/2020
f1_keywords:
- VC.Project.VCCLCompilerTool.EnablePREfast
- /analyze
- VC.Project.VCCLCompilerTool.PREfastAdditionalOptions
- VC.Project.VCCLCompilerTool.PREfastAdditionalPlugins
helpviewer_keywords:
- /analyze compiler option [C++]
- -analyze compiler option [C++]
- analyze compiler option [C++]
ms.assetid: 81da536a-e030-4bd4-be18-383927597d08
ms.openlocfilehash: e970872e89132aed52190b8688f2cdaccab5ea6f
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91500091"
---
# <a name="analyze-code-analysis"></a>`/analyze` (Анализ кода)

Включает анализ кода и параметры управления.

## <a name="syntax"></a>Синтаксис

::: moniker range=">=vs-2017"

> **`/analyze`**\
> **`/analyze-`**\
> **`/analyze:autolog`**\
> **`/analyze:autolog-`**\
> **`/analyze:autolog:ext`***расширение*\
> **`/analyze:log`***имя файла*\
> **`/analyze:max_paths`***число*\
> **`/analyze:only`**\
> **`/analyze:plugin`***подключаемый модуль — DLL*\
> **`/analyze:quiet`**\
> **`/analyze:ruleset`** набор *правил*\
> **`/analyze:stacksize`***число*\
> **`/analyze:WX-`**

::: moniker-end
::: moniker range="vs-2015"

> **`/analyze`**\
> **`/analyze-`**\
> **`/analyze:autolog`**\
> **`/analyze:autolog-`**\
> **`/analyze:autolog:ext`***расширение*\
> **`/analyze:log`***имя файла*\
> **`/analyze:max_paths`***число*\
> **`/analyze:only`**\
> **`/analyze:plugin`***подключаемый модуль — DLL*\
> **`/analyze:quiet`**\
> **`/analyze:stacksize`***число*\
> **`/analyze:WX-`**

::: moniker-end

## <a name="arguments"></a>Аргументы

**`/analyze`**\
Включает анализ в режиме по умолчанию. Результаты анализа передаются в консоль или в окно **вывода** Visual Studio, как и другие сообщения об ошибках. Используйте **`/analyze-`** , чтобы явно отключить анализ.

**`/analyze:autolog`**\
Подробные результаты анализатора записываются в виде XML в файл с тем же базовым именем, что и у исходного файла, и расширением *`.pftlog`* . **`/analyze:autolog-`** отключает этот файл журнала.

**`/analyze:autolog:ext`***расширение*\
Подробные результаты анализатора записываются в виде XML в файл с тем же базовым именем, что и у исходного файла, и расширением *расширения*.

**`/analyze:log`***имя файла*\
Подробные результаты анализа записываются в формате XML в файл, указанный в параметре *filename*.

**`/analyze:max_paths`***число*\
Параметр *Number* , используемый с этим параметром, задает максимальное количество ветвей кода для анализа. Если этот параметр не указан, по умолчанию используется значение 256. Большие значения приводят к более тщательной проверке, но анализ может занять больше времени.

**`/analyze:only`**\
Обычно после завершения работы анализатора компилятор создает код и производит дополнительную проверку синтаксиса. **`/analyze:only`** Параметр отключает этот проход создания кода. Он ускоряет анализ, но не выдает ошибок компилятора и предупреждений о том, что может обнаружиться этап создания кода компилятора. Если программа не освобождает ошибки создания кода, результаты анализа могут быть ненадежными. Этот параметр рекомендуется использовать, только если код уже прошел проверку синтаксиса создания кода без ошибок.

**`/analyze:plugin`***подключаемый модуль — DLL*\
Включает указанный быстрый подключаемый модуль в ходе выполнения анализа кода.

::: moniker range="<=vs-2017"

LocalEspC.dll — это подключаемый модуль, реализующий проверки кода, связанные с параллелизмом, в диапазоне предупреждений C261XX. Например, [C26100](../../code-quality/c26100.md), [C26101](../../code-quality/c26101.md),...,  [C26167](../../code-quality/c26167.md).

Чтобы запустить LocalEspC.dll, используйте следующий параметр компилятора: **`/analyze:plugin LocalEspC.dll`**

::: moniker-end
::: moniker range=">=vs-2019"

ConcurrencyCheck.dll реализует проверки кода, связанные с параллелизмом, в диапазоне предупреждений C261XX. Например, [C26100](../../code-quality/c26100.md), [C26101](../../code-quality/c26101.md),...,  [C26167](../../code-quality/c26167.md).

Чтобы запустить ConcurrencyCheck.dll, сначала выполните эту команду в командной строке разработчика:

```cmd
set Esp.Extensions=ConcurrencyCheck.dll
```

Затем используйте этот параметр компилятора: **`/analyze:plugin EspXEngine.dll`** .

Чтобы запустить CppCoreCheck.dll, сначала выполните эту команду в командной строке разработчика:

```cmd
set Esp.Extensions=CppCoreCheck.dll
```

Затем используйте этот параметр компилятора: **`/analyze:plugin EspXEngine.dll`** .

::: moniker-end

**`/analyze:quiet`**\
Отключает вывод анализатора на консоли или в окне **вывода** Visual Studio.

::: moniker range=">=vs-2017"

**`/analyze:ruleset`***FILE_PATH. RuleSet*\
Позволяет указать, какие наборы правил следует анализировать, включая настраиваемые наборы правил, которые можно создать самостоятельно. Если этот параметр задан, обработчик правил более эффективен, так как перед выполнением исключает элементы, не являющиеся членами указанного набора правил. В противном случае подсистема проверяет все правила.

Наборы правил, поставляемые с Visual Studio, находятся в *`%VSINSTALLDIR%\Team Tools\Static Analysis Tools\Rule Sets`* .

В следующем образце настраиваемого набора правил обработчик правил проверяет наличие C6001 и C26494. Этот файл можно поместить в любое место, если он имеет *`.ruleset`* расширение, и указать полный путь в аргументе.

```xml
<?xml version="1.0" encoding="utf-8"?>
<RuleSet Name="New Rule Set" Description="New rules to apply." ToolsVersion="15.0">
  <Rules AnalyzerId="Microsoft.Analyzers.NativeCodeAnalysis" RuleNamespace="Microsoft.Rules.Native">
    <Rule Id="C6001" Action="Warning" />
    <Rule Id="C26494" Action="Warning" />
  </Rules>
</RuleSet>
```

::: moniker-end

**`/analyze:stacksize`***число*\
Параметр *Number* , используемый с этим параметром, задает размер (в байтах) кадра стека, для которого создается предупреждение [C6262](../../code-quality/c6262.md) . Пробел перед *числом* является необязательным. Если этот параметр не указан, по умолчанию размер кадра стека — 16 КБ.

**`/analyze:WX-`**\
Предупреждения анализа кода не обрабатываются как ошибки при компиляции с помощью **`/WX`** . Дополнительные сведения см. в разделе [ `/WX` (уровень предупреждений)](compiler-option-warning-level.md).

## <a name="remarks"></a>Remarks

Дополнительные сведения см. в разделе [анализ кода для c/c++ обзор](../../code-quality/code-analysis-for-c-cpp-overview.md) и [анализ кода для предупреждений c/c++](../../code-quality/code-analysis-for-c-cpp-warnings.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Выберите страницу свойств **Свойства конфигурации**  >  **Code Analysis**  >  **Общие** свойства анализ кода.

1. Измените одно или несколько свойств **анализа кода** .

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

1. См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnablePREfast%2A>.

## <a name="see-also"></a>См. также раздел

[Параметры компилятора КОМПИЛЯТОРОМ MSVC](compiler-options.md)\
[Синтаксис командной строки компилятора КОМПИЛЯТОРОМ MSVC](compiler-command-line-syntax.md)
