---
title: "-w-W0,-W1, - W2,-W3, - W4,-w1,-w2,-w3,-w4,-Wall, -wd,-мы -wo, -Wv, - WX (порог предупреждений) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.DisableSpecificWarnings
- VC.Project.VCCLCompilerTool.WarningLevel
- VC.Project.VCCLWCECompilerTool.DisableSpecificWarnings
- VC.Project.VCCLCompilerTool.WarnAsError
- VC.Project.VCCLWCECompilerTool.WarnAsError
- /wx
- VC.Project.VCCLWCECompilerTool.WarningLevel
- /wall
- VC.Project.VCCLCompilerTool.TreatSpecificWarningsAsErrors
- /Wv
- /w0
- /w1
- /w2
- /w3
- /w4
- /wd
- /we
- /wo
dev_langs: C++
helpviewer_keywords:
- /W1 compiler option [C++]
- w compiler option [C++]
- -wo compiler option [C++]
- Warning Level compiler option
- W1 compiler option [C++]
- -we compiler option [C++]
- /WX compiler option [C++]
- -wd compiler option [C++]
- WX compiler option [C++]
- wo compiler option [C++]
- Wall compiler option [C++]
- /w compiler option
- W2 compiler option [C++]
- -W2 compiler option [C++]
- wd compiler option [C++]
- /we compiler option [C++]
- we compiler option [C++]
- -W1 compiler option [C++]
- -W4 compiler option [C++]
- -Wall compiler option [C++]
- /Wall compiler option [C++]
- -W0 compiler option [C++]
- W0 compiler option [C++]
- -WX compiler option [C++]
- /wo compiler option [C++]
- W4 compiler option [C++]
- W3 compiler option [C++]
- /wd compiler option [C++]
- warnings, as errors compiler option
- /W3 compiler option [C++]
- /W0 compiler option [C++]
- /W4 compiler option [C++]
- -W3 compiler option [C++]
- -w compiler option [C++]
- /W2 compiler option [C++]
- /Wv compiler option [C++]
ms.assetid: d6bc7bf5-c754-4879-909c-8e3a67e2629f
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4f38328f94fd68b3b5402d08ddb6d2bd97e3de76
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="w-w0-w1-w2-w3-w4-w1-w2-w3-w4-wall-wd-we-wo-wv-wx-warning-level"></a>/ w, помощью/W0, /W1, /W2, /W3, / W4, /w1, /w2, /w3, / W4, / Wall, /wd, и мы /wo, / wv, / WX (порог предупреждений)
Указывает, как компилятор создает предупреждения для данной компиляции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/w  
/W0  
/W1  
/W2  
/W3  
/W4  
/Wall  
/Wv[<version>]  
/WX  
/w1<warning>   
/w2<warning>   
/w3<warning>   
/w4<warning>   
/wd<warning>   
/we<warning>   
/wo<warning>  
```  
  
## <a name="remarks"></a>Примечания  
 Параметры предупреждения определяют, какие предупреждения компилятора для отображения и поведения предупреждения для всей компиляции.  
  
 В следующей таблице описаны предупреждений и связанных аргументов.  
  
|Параметр|Описание:|  
|------------|-----------------|  
|**/w**|Отключает все предупреждения компилятора.|  
|**/W0**<br /><br /> **/W1**<br /><br /> **/W2**<br /><br /> **/W3**<br /><br /> **/W4**|Задает уровень предупреждений, создаваемой компилятором. Предупреждение допустимые уровни в диапазоне от 0 до 4:<br /><br /> -   **/ W0** отключает все предупреждения.<br />-   **/ W1** отображает предупреждения (серьезность) уровня 1. **/ W1** параметр по умолчанию.<br />-   **/ W2** отображает уровня 1 и предупреждения уровня 2 (значительные).<br />-   **/ W3** отображает уровень 1, уровень 2 и 3 предупреждения (производственного качества) уровня.<br />-   **/ W4** отображает уровня 1, 2, уровня и уровня 3 предупреждения, а также все уровня 4 (информационное) предупреждений, которые не отключены по умолчанию. Мы рекомендуем использовать этот параметр, только для предоставления корпус подобные предупреждения. Однако для нового проекта, возможно, лучше всего использовать **/W4** во всех компиляциях; это позволит гарантировать находимых ошибок кода жестких для поиска.|  
|**/ Wall**|Отображает все предупреждения, отображаемого элементом **/W4** и все другие предупреждения, **/W4** не включает — например, предупреждения, отключенные по умолчанию. Дополнительные сведения см. в разделе [компилятора предупреждения, которые отключено по умолчанию](../../preprocessor/compiler-warnings-that-are-off-by-default.md).|  
|**/ Wv**`:version`|Подавлять предупреждения, появившиеся в версиях, более новой версии компилятора `version`. Этот параметр можно использовать для определения новых предупреждений в код, скомпилированный без предупреждения при использовании более старой версии компилятора и чтобы временно отключить новые предупреждения от процесса сборки во время их исправления. Необязательный параметр `version` принимает форму `nn`[.`mm` [. `bbbbb`]] где `nn` является основной номер версии, `mm` имеет необязательный дополнительный номер версии, и `bbbbb` — номер сборки необязательно компилятора. Например, использовать `/Wv:17.00.00000` для подавления предупреждения, появившиеся в Visual C++ 2012 и более поздних версий. По умолчанию **/wv** использует номер текущей версии компилятора и предупреждений, подавляются. Сведения о том, какие предупреждения подавляются по версии компилятора см. в разделе [предупреждения компилятора, версия компилятора](../..//error-messages/compiler-warnings/compiler-warnings-by-compiler-version.md).|  
|**/ WX**|Интерпретирует все предупреждения компилятора как ошибки. Для нового проекта, возможно, лучше всего использовать **/WX** во всех компиляциях; разрешение всех предупреждений гарантирует находимых ошибок кода жестких для поиска.<br /><br /> Компоновщик также имеет **/WX** параметр. Дополнительные сведения см. в разделе [Параметр /WX (обработка предупреждений компоновщика как ошибок)](../../build/reference/wx-treat-linker-warnings-as-errors.md).|  
|**/W1**`n`<br /><br /> **/W2**`n`<br /><br /> **/W3**`n`<br /><br /> **/ W4**`n`|Задает уровень предупреждений для предупреждения числу, указанному в `n`. Это позволяет изменять поведение компилятора для этого предупреждения, когда значение определенного уровня предупреждения. Эти параметры можно использовать в сочетании с другими параметрами предупреждение для применения собственного кода стандартов для предупреждения, а не по умолчанию, предоставляемые Visual Studio.<br /><br /> Например `/w34326` вызывает C4326 необходимо создать как предупреждение уровня 3 вместо уровня 1. Если компиляция выполняется с использованием `/w34326` параметр и `/W2` параметр, предупреждение C4326 не создается.|  
|**/wd**`n`|Подавляет предупреждение компилятора, который задается параметром `n`.<br /><br /> Например `/wd4326` подавляет предупреждение компилятора C4326.|  
|**/we**`n`|Предупреждение компилятора, который задается параметром рассматривает `n` как ошибку.<br /><br /> Например `/we4326` вызывает предупреждение из C4326 рассматривается как ошибка компилятором.|  
|**/WO**`n`|Отчеты, Предупреждение компилятора, указанные в `n` только один раз.<br /><br /> Например `/wo4326` причин предупреждение C4326 возвращаются только один раз, в первый раз его обнаружении компилятором.|  
  
 При использовании любого параметра предупреждение при создании предкомпилированного заголовка с помощью [/Yc](../../build/reference/yc-create-precompiled-header-file.md) любое использование предварительно скомпилированного заголовка с помощью параметра [/Yu](../../build/reference/yu-use-precompiled-header-file.md) вынуждает те же параметры предупреждение вступил в силу еще раз. Можно переопределить параметры предупреждения, заданные в предварительно скомпилированного заголовка с помощью другого параметра предупреждение в командной строке.  
  
 Можно использовать [#pragma warning](../../preprocessor/warning.md) директиву, чтобы управлять уровнем предупреждение, указанная во время компиляции в определенных исходных файлов.  
  
 Предупреждение директивы pragma в исходном коде не подвержены влиянию **/w** параметр.  
  
 [Построения документации ошибки](../../error-messages/compiler-errors-1/c-cpp-build-errors.md) описывает предупреждений и порогов предупреждения и показывает, почему некоторые операторы, может не компилироваться как предполагается.  
  
### <a name="to-set-the-compiler-option-in-the-visual-studio-development-environment"></a>Установка параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Выберите **C/C++**.  
  
3.  На **Общие** свойства, измените **уровень предупреждений** или **обрабатывать предупреждения как ошибки** свойства.  
  
4.  На **Дополнительно** свойства, измените **отключить определенные предупреждения** свойство.  
  
5.  Для остальных параметров на **командной строки** свойства введите параметр компилятора в **Дополнительные параметры** поле.  
  
### <a name="to-set-the-compiler-option-programmatically"></a>Установка параметра компилятора программным способом  
  
-   См. разделы <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.WarningLevel%2A>, <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.WarnAsError%2A>, <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DisableSpecificWarnings%2A> и <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)