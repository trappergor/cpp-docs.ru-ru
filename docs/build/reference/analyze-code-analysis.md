---
title: -analyze (анализ кода) | Документация Майкрософт
ms.custom: ''
ms.date: 04/26/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.EnablePREfast
- /analyze
- VC.Project.VCCLCompilerTool.PREfastAdditionalOptions
- VC.Project.VCCLCompilerTool.PREfastAdditionalPlugins
dev_langs:
- C++
helpviewer_keywords:
- /analyze compiler option [C++]
- -analyze compiler option [C++]
- analyze compiler option [C++]
ms.assetid: 81da536a-e030-4bd4-be18-383927597d08
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 89f0402eedbe6e49d6ce4095dc8c91ec69e15447
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45723610"
---
# <a name="analyze-code-analysis"></a>/analyze (анализ кода)

Включает анализ кода и параметры управления.

## <a name="syntax"></a>Синтаксис

```cmd
/analyze[-][:WX-][:log filename][:quiet][:stacksize number][:max_paths number][:only][:ruleset]
```

## <a name="arguments"></a>Аргументы

/ analyze включает анализ в режиме по умолчанию. Результат анализа выводится в **вывода** окна, как и другие сообщения об ошибках. Используйте **/ analyze-** чтобы явно отключить анализ.

/ analyze: WX-задание **/ analyze: WX -** означает, что предупреждения анализа кода не обрабатываются как ошибки при компиляции с помощью **/WX**. Дополнительные сведения см. в разделах [/w, /W0, /W1, /W2, /W3, /W4, /w1, /w2, /w3, /w4, /Wall, /wd, /we, /wo, /Wv, /WX (уровень предупреждений)](../../build/reference/compiler-option-warning-level.md).

/ analyze: журнал `filename` подробные результаты анализатора записываются в формате XML в файл, который задается параметром `filename`.

/ analyze: quiet включение, отключение вывод данных анализатора в **вывода** окна.

/ analyze: stacksize `number` `number` параметр, используемый с этим параметром указывает размер в байтах, кадра стека для какие предупреждения [C6262](/visualstudio/code-quality/c6262) создается. Если этот параметр не указан, по умолчанию кадр стека имеет размер 16 КБ.

/ analyze: max_paths `number` `number` параметр, используемый с помощью этого параметра указывает максимальное количество анализируемых путей кода. Если этот параметр не указан, значение по умолчанию равно 256. Большие значения обеспечивают более тщательную проверку, но анализ может выполняться дольше.

/ analyze: только как правило, компилятор создает код и производит дополнительную проверку после работы анализатора синтаксиса. **/ Analyze: только** параметр отключает этот проход для создания кода; анализ ускоряется, но не выдаются ошибки и предупреждения, которые могли быть обнаружены на проходе создания кода компилятора. Если в программе имеются ошибки создания кода, результаты анализа могут быть недостоверны; поэтому рекомендуется использовать этот параметр только в том случае, если код уже без ошибок прошел проверку синтаксиса создания кода.

/ analyze: ruleset `<file_path>.ruleset` позволяет указать, какое правило задает для анализа, включая настраиваемых наборов правил, можно создать самостоятельно. Если этот переключатель установлен, обработчик правил является более эффективным, поскольку исключает от членов указанного набора перед выполнением правил. Если параметр не задан, обработчик выполняет проверку всех правил.

Наборы правил, входящие в состав Visual Studio можно найти в **%VSINSTALLDIR%\Team Tools\Static Analysis Tools\Rule наборов.**

Следующий пример настраиваемый набор правил подсистема обработки правил для проверки наличия C6001 и C26494. Этот файл можно разместить где угодно, пока он имеет `.ruleset` расширения и укажите полный путь в качестве аргумента.

```xml
<?xml version="1.0" encoding="utf-8"?>
<RuleSet Name="New Rule Set" Description=" " ToolsVersion="15.0">
  <Rules AnalyzerId="Microsoft.Analyzers.NativeCodeAnalysis" RuleNamespace="Microsoft.Rules.Native">
    <Rule Id="C6001" Action="Warning" />
    <Rule Id="C26494" Action="Warning" />
  </Rules>
</RuleSet>
```

/ analyze: подключаемый модуль позволяет PREfast указанный подключаемый модуль, как часть анализа кода работает.
LocalEspC.dll — это подключаемый модуль, который реализует анализ кода, связанные с параллелизмом проверяет в диапазон от C261XX предупреждения. Например [C26100](/visualstudio/code-quality/c26100), [C26101](/visualstudio/code-quality/c26101),..., [C26167](/visualstudio/code-quality/c26167).

Чтобы запустить LocalEspC.dll, используйте этот параметр компилятора: **/ analyze: подключаемый модуль LocalEspC.dll**

Чтобы запустить CppCoreCheck.dll, сначала выполните следующую команду из командной строки разработчика:

```cmd
set Esp.Extensions=CppCoreCheck.dll
```

Затем используйте этот параметр компилятора: **/ analyze: подключаемый модуль EspXEngine.dll**.

## <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [анализ кода для C/C++ Обзор](/visualstudio/code-quality/code-analysis-for-c-cpp-overview) и [анализ кода для предупреждений C/C++](/visualstudio/code-quality/code-analysis-for-c-cpp-warnings).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Разверните узел **Свойства конфигурации**.

1. Разверните **анализа кода** узла.

1. Выберите страницу свойств **Общие** .

1. Измените одно или несколько из **анализа кода** свойства.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

1. См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnablePREfast%2A>.

## <a name="see-also"></a>См. также

- [Параметры компилятора](../../build/reference/compiler-options.md)
- [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)