---
title: /analyze (анализ кода)
ms.date: 10/15/2019
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
ms.openlocfilehash: f537fdea2703805c7ab1c57ba0d4429f6b683ae4
ms.sourcegitcommit: 9aab425662a66825772f091112986952f341f7c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72444897"
---
# <a name="analyze-code-analysis"></a>/analyze (анализ кода)

Включает анализ кода и параметры управления.

## <a name="syntax"></a>Синтаксис

> **/Analyze**[-] [ **: WX-** ] [ **:** *имя файла*журнала] [:**quiet**] [ **: STACKSIZE** *номер*] **[: max_paths** *номер*] [ **: только**] [ **: RuleSet** *RuleSet*] [ **:p Лугин**  *plugin-DLL*]

## <a name="arguments"></a>Аргументы

**/analyze**\
Включает анализ в режиме по умолчанию. Результаты анализа передаются в окно **вывода** , как и другие сообщения об ошибках. Используйте **/анализе-** , чтобы явно отключить анализ.

**/Analyze: WX-** \
Предупреждения анализа кода не обрабатываются как ошибки при компиляции с помощью **/WX**. Дополнительные сведения см. в разделе [/WX (уровень предупреждений)](compiler-option-warning-level.md).

**/Analyze:** *имя файла*журнала \
Подробные результаты анализа записываются в формате XML в файл, указанный в параметре *filename*.

**/Analyze: quiet**\
Отключает вывод анализатора в окне **вывода** .

**/Analyze: STACKSIZE** *Number*\
Параметр *Number* , используемый с этим параметром, задает размер (в байтах) кадра стека, для которого создается предупреждение [C6262](/visualstudio/code-quality/c6262) . Пробел перед *числом* является необязательным. Если этот параметр не указан, по умолчанию размер кадра стека — 16 КБ.

**/Analyze: max_paths** *Number*\
Параметр *Number* , используемый с этим параметром, задает максимальное количество ветвей кода для анализа. Если этот параметр не указан, по умолчанию используется значение 256. Большие значения приводят к более тщательной проверке, но анализ может занять больше времени.

**/Analyze: только**\
Обычно после завершения работы анализатора компилятор создает код и производит дополнительную проверку синтаксиса. Параметр **/Analyze: only** отключает этот проход создания кода. Он быстрее выполняет анализ, но компилирует ошибки и предупреждения, которые могут быть не выданы компилятором при создании кода. Если программа не освобождает ошибки создания кода, результаты анализа могут быть ненадежными. Этот параметр рекомендуется использовать, только если код уже прошел проверку синтаксиса создания кода без ошибок.

**/Analyze: RuleSet** *file_path. RuleSet*\
Позволяет указать, какие наборы правил следует анализировать, включая настраиваемые наборы правил, которые можно создать самостоятельно. Если этот параметр задан, обработчик правил более эффективен, так как перед выполнением исключает элементы, не являющиеся членами указанного набора правил. В противном случае подсистема проверяет все правила.

Наборы правил, поставляемые с Visual Studio, находятся в *наборах%Всинсталлдир%\теам Тулс\статик Analysis Тулс\руле Sets.*

В следующем образце настраиваемого набора правил обработчик правил проверяет наличие C6001 и C26494. Этот файл можно поместить в любое место при условии, что он имеет расширение `.ruleset`, и указать полный путь в аргументе.

```xml
<?xml version="1.0" encoding="utf-8"?>
<RuleSet Name="New Rule Set" Description=" " ToolsVersion="15.0">
  <Rules AnalyzerId="Microsoft.Analyzers.NativeCodeAnalysis" RuleNamespace="Microsoft.Rules.Native">
    <Rule Id="C6001" Action="Warning" />
    <Rule Id="C26494" Action="Warning" />
  </Rules>
</RuleSet>
```

**/Analyze:** *подключаемый модуль*подключаемого модуля — DLL \
Включает указанный быстрый подключаемый модуль в ходе выполнения анализа кода.

::: moniker range="<=vs-2017"

Локалеспк. dll — это подключаемый модуль, реализующий проверки кода, связанные с параллелизмом, в диапазоне предупреждений C261XX. Например, [C26100](/visualstudio/code-quality/c26100), [C26101](/visualstudio/code-quality/c26101),..., [C26167](/visualstudio/code-quality/c26167).

Чтобы запустить Локалеспк. dll, используйте следующий параметр компилятора: **/Analyze: plugin локалеспк. dll**

::: moniker-end
::: moniker range=">=vs-2019"

ConcurrencyCheck. DLL реализует проверку кода, связанную с параллелизмом, в диапазоне предупреждений C261XX. Например, [C26100](/visualstudio/code-quality/c26100), [C26101](/visualstudio/code-quality/c26101),..., [C26167](/visualstudio/code-quality/c26167).

Чтобы запустить ConcurrencyCheck. dll, сначала выполните эту команду в командной строке разработчика:

```cmd
set Esp.Extensions=ConcurrencyCheck.dll
```

Затем используйте этот параметр компилятора: **/Analyze: plugin еспксенгине. dll**.

::: moniker-end

Чтобы запустить CppCoreCheck. dll, сначала выполните эту команду в командной строке разработчика:

```cmd
set Esp.Extensions=CppCoreCheck.dll
```

Затем используйте этот параметр компилятора: **/Analyze: plugin еспксенгине. dll**.

## <a name="remarks"></a>Заметки

Дополнительные сведения см. в разделе [анализ кода для cC++ /обзор](/visualstudio/code-quality/code-analysis-for-c-cpp-overview) и [анализ кода для cC++ /Warnings](/visualstudio/code-quality/code-analysis-for-c-cpp-warnings).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Выберите **Свойства конфигурации** > **анализ кода** > **Общая** страница свойств.

1. Измените одно или несколько свойств **анализа кода** .

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

1. См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnablePREfast%2A>.

## <a name="see-also"></a>См. также

[Параметры компилятора компилятором msvc](compiler-options.md)\
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)
