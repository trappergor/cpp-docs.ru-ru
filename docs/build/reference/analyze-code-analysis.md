---
title: -analyze (анализ кода) | Документы Microsoft
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
ms.openlocfilehash: 4893f30bae3b29538c8bead637cb4d083087a57b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="analyze-code-analysis"></a>/analyze (анализ кода)

Включает анализ кода и параметры управления.

## <a name="syntax"></a>Синтаксис

```cmd
/analyze[-][:WX-][:log filename][:quiet][:stacksize number][:max_paths number][:only][:ruleset]
```

## <a name="arguments"></a>Аргументы

 /analyze  
 Включает анализ в режиме по умолчанию. Результат анализа выводится в **вывода** как другие сообщения об ошибках. Используйте **/ analyze-** явно отключить анализ.

 /analyze:WX-  
 Указание **/ analyze: WX -** означает, что предупреждения анализа кода не обрабатываются как ошибки при компиляции с помощью **/WX**. Дополнительные сведения см. в разделах [/w, /W0, /W1, /W2, /W3, /W4, /w1, /w2, /w3, /w4, /Wall, /wd, /we, /wo, /Wv, /WX (уровень предупреждений)](../../build/reference/compiler-option-warning-level.md).

 /analyze:log `filename`  
 Подробные результаты анализатора записываются в формате XML в файл, который задается параметром `filename`.

 /analyze:quiet  
 Отключает вывод данных анализатора в **вывода** окна.

 /analyze:stacksize `number`  
 `number` Параметр, используемый с этим параметром указывает размер в байтах кадра стека, для которых предупреждение [C6262](/visualstudio/code-quality/c6262) создается. Если этот параметр не указан, по умолчанию кадр стека имеет размер 16 КБ.

 /analyze:max_paths `number`  
 Параметр `number`, используемый с этим параметром, задает максимальное количество анализируемых путей кода. Если этот параметр не указан, значение по умолчанию равно 256. Большие значения обеспечивают более тщательную проверку, но анализ может выполняться дольше.

 /analyze:only  
 Обычно после завершения работы анализатора компилятор создает код и производит дополнительную проверку синтаксиса. **/ Analyze: только** отключает этот проход для создания кода; анализ ускоряется, но ошибки и предупреждения, которые могли быть обнаружены на проходе создания кода компилятор не выдаются. Если в программе имеются ошибки создания кода, результаты анализа могут быть недостоверны; поэтому рекомендуется использовать этот параметр только в том случае, если код уже без ошибок прошел проверку синтаксиса создания кода.

 / analyze: набора правил `<file_path>.ruleset`  
Позволяет указать, какое правило задает для анализа, включая настраиваемых наборов правил, можно создать самостоятельно. Если этот параметр задан, обработчик правил более эффективна, так как он исключает не элементы указанного набора, перед выполнением правил. Если параметр не задан, ядро проверяет все правила.

Наборы правил, которые поставляются вместе с Visual Studio можно найти на **%VSINSTALLDIR%\Team Tools\Static Analysis Tools\Rule наборов.**

Следующий пример настраиваемый набор правил подсистема обработки правил для проверки наличия C6001 и C26494. Этот файл можно поместить в любом месте при условии, что он имеет `.ruleset` расширение и можно указывать полный путь в качестве аргумента.

```xml
<?xml version="1.0" encoding="utf-8"?>
<RuleSet Name="New Rule Set" Description=" " ToolsVersion="15.0">
  <Rules AnalyzerId="Microsoft.Analyzers.NativeCodeAnalysis" RuleNamespace="Microsoft.Rules.Native">
    <Rule Id="C6001" Action="Warning" />
    <Rule Id="C26494" Action="Warning" />
  </Rules>
</RuleSet>
```

/ analyze: подключаемый модуль  
Включает указанный подключаемый модуль PREfast во время выполнения в ходе анализа кода. LocalEspC.dll — проверяет, подключаемый модуль, реализующий анализа кода, связанные с параллелизмом в диапазоне C261XX предупреждения. Например [C26100](/visualstudio/code-quality/c26100), [C26101](/visualstudio/code-quality/c26101),..., [C26167](/visualstudio/code-quality/c26167).

Чтобы запустить LocalEspC.dll, используйте этот параметр компилятора: **/ analyze: подключаемый модуль LocalEspC.dll**

Чтобы запустить CppCoreCheck.dll, сначала выполните следующую команду из командной строки разработчика:

```cmd
set Esp.Extensions=CppCoreCheck.dll
```

Затем используйте этот параметр компилятора: **/ analyze: подключаемый модуль EspXEngine.dll**.

## <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [анализа кода C/C++ Обзор](/visualstudio/code-quality/code-analysis-for-c-cpp-overview) и [анализ кода для предупреждений C/C++](/visualstudio/code-quality/code-analysis-for-c-cpp-warnings).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Разверните **свойства конфигурации** узла.

1. Разверните **анализа кода** узла.

1. Выберите страницу свойств **Общие** .

1. Измените одно или несколько **анализа кода** свойства.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

1. См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnablePREfast%2A>.

## <a name="see-also"></a>См. также

- [Параметры компилятора](../../build/reference/compiler-options.md)
- [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)