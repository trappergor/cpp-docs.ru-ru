---
title: "-analyze (анализ кода) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ba76ddd10866e414d9817f628c7a1aec019964de
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="analyze-code-analysis"></a>/analyze (анализ кода)
Включает анализ кода и параметры управления.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/analyze[-][:WX-][:log filename][:quiet][:stacksize number][:max_paths number][:only]  
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
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [анализа кода C/C++ Обзор](/visualstudio/code-quality/code-analysis-for-c-cpp-overview) и [анализ кода для предупреждений C/C++](/visualstudio/code-quality/code-analysis-for-c-cpp-warnings).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Разверните **свойства конфигурации** узла.  
  
3.  Разверните **анализа кода** узла.  
  
4.  Выберите страницу свойств **Общие** .  
  
5.  Измените одно или несколько **анализа кода** свойства.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом  
  
1.  См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnablePREfast%2A>.  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)