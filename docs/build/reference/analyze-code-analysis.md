---
title: /analyze (анализ кода)
ms.date: 10/01/2019
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
ms.openlocfilehash: d647045d76dc32544f8146424b220547890b0943
ms.sourcegitcommit: 4517932a67bbf2db16cfb122d3bef57a43696242
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2019
ms.locfileid: "71816334"
---
# <a name="analyze-code-analysis"></a>/analyze (анализ кода)

Включает анализ кода и параметры управления.

## <a name="syntax"></a>Синтаксис

```cmd
/analyze[-][:WX-][:log filename][:quiet][:stacksize number][:max_paths number][:only][:ruleset]
```

## <a name="arguments"></a>Аргументы

/Analyze включает анализ в режиме по умолчанию. Результаты анализа передаются в окно **вывода** , как и другие сообщения об ошибках. Используйте **/анализе-** , чтобы явно отключить анализ.

/Analyze: WX — указание **/Analyze: WX —** означает, что предупреждения анализа кода не обрабатываются как ошибки при компиляции с помощью параметра **/WX**. Дополнительные сведения см. в разделах [/w, /W0, /W1, /W2, /W3, /W4, /w1, /w2, /w3, /w4, /Wall, /wd, /we, /wo, /Wv, /WX (уровень предупреждений)](compiler-option-warning-level.md).

/Analyze: log `filename` подробные результаты анализатора записываются в файл в формате XML, указанном параметром `filename`.

/Analyze: quiet отключает вывод анализатора в окне **вывода** .

/Analyze: STACKSIZE `number`. параметр `number`, используемый с этим параметром, задает размер (в байтах) кадра стека, для которого создается предупреждение [C6262](/visualstudio/code-quality/c6262) . Пробел до `number` является необязательным. Если этот параметр не указан, по умолчанию кадр стека имеет размер 16 КБ.

/Analyze: max_paths `number`. параметр `number`, используемый с этим параметром, задает максимальное количество ветвей кода для анализа. Если этот параметр не указан, значение по умолчанию равно 256. Большие значения обеспечивают более тщательную проверку, но анализ может выполняться дольше.

/Analyze: обычно компилятор создает код и выполняет дополнительную проверку синтаксиса после запуска анализатора. Параметр **/Analyze: only** отключает этот проход создания кода; Это ускоряет анализ, но ошибки компиляции и предупреждения, которые могли быть обнаружены в ходе создания кода компилятора, не создаются. Если в программе имеются ошибки создания кода, результаты анализа могут быть недостоверны; поэтому рекомендуется использовать этот параметр только в том случае, если код уже без ошибок прошел проверку синтаксиса создания кода.

/Analyze: RuleSet `<file_path>.ruleset` позволяет указать, какие наборы правил следует анализировать, включая настраиваемые наборы правил, которые можно создать самостоятельно. Если этот параметр задан, обработчик правил более эффективен, так как перед запуском исключены не члены указанного набора правил. Если параметр не задан, подсистема проверяет все правила.

Наборы правил, поставляемые с Visual Studio, находятся в **наборах%Всинсталлдир%\теам Тулс\статик Analysis Тулс\руле Sets.**

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

/Analyze: подключаемый модуль включает в ходе анализа кода указанный быстрый подключаемый модуль.
Локалеспк. dll — это подключаемый модуль, реализующий проверки кода, связанные с параллелизмом, в диапазоне предупреждений C261XX. Например, [C26100](/visualstudio/code-quality/c26100), [C26101](/visualstudio/code-quality/c26101),..., [C26167](/visualstudio/code-quality/c26167).

Чтобы запустить Локалеспк. dll, используйте следующий параметр компилятора: **/Analyze: plugin локалеспк. dll**

Чтобы запустить CppCoreCheck. dll, сначала выполните эту команду в командной строке разработчика:

```cmd
set Esp.Extensions=CppCoreCheck.dll
```

Затем используйте этот параметр компилятора: **/Analyze: plugin еспксенгине. dll**.

## <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [анализ кода для cC++ /обзор](/visualstudio/code-quality/code-analysis-for-c-cpp-overview) и [анализ кода для cC++ /Warnings](/visualstudio/code-quality/code-analysis-for-c-cpp-warnings).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Разверните узел **Свойства конфигурации**.

1. Разверните узел **анализ кода** .

1. Выберите страницу свойств **Общие** .

1. Измените одно или несколько свойств **анализа кода** .

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

1. См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnablePREfast%2A>.

## <a name="see-also"></a>См. также

- [Параметры компилятора MSVC](compiler-options.md)
- [Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)
