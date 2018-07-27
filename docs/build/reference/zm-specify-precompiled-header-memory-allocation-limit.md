---
title: -Zm (задание ограничения выделения памяти для предкомпилированного заголовка) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /zm
dev_langs:
- C++
helpviewer_keywords:
- PCH files, memory allocation limit
- Zm compiler option [C++]
- /Zm compiler option [C++]
- precompiled header files, memory allocation limit
- Specify Precompiled Header Memory Allocation Limit compiler option
- cl.exe compiler, memory allocation limit
- .pch files, memory allocation limit
- memory allocation, Memory Allocation Limit compiler option
- -Zm compiler option [C++]
ms.assetid: 94c77d5e-6672-46a7-92e0-3f69e277727d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 379d3d6673e673522334d685a47220bcfa2523ec
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32380905"
---
# <a name="zm-specify-precompiled-header-memory-allocation-limit"></a>/Zm (задание ограничения выделения памяти для предкомпилированного заголовка)
Этот параметр задает объем памяти, который выделяется компилятором для конструирования предкомпилированных заголовков.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/Zmfactor  
```  
  
## <a name="arguments"></a>Аргументы  
 `factor`  
 Коэффициент масштабирования, определяющий объем памяти, используемый компилятором для конструирования предкомпилированных заголовков.  
  
 Аргумент `factor` представляет собой долю в процентах от размера по умолчанию рабочего буфера, заданного компилятором. Значение по умолчанию аргумента `factor` — 100 (процентов), но можно указать большее или меньшее значение.  
  
## <a name="remarks"></a>Примечания  
 В предыдущих версиях Visual C++ компилятор использовал несколько отдельных куч, размер каждой из которых был ограничен. В настоящее время компилятор динамически увеличивает кучи по мере необходимости вплоть до общего предела размера куч; буфер фиксированного размера требуется только для конструирования предкомпилированных заголовков. Следовательно **/Zm** параметр компилятора требуется редко.  
  
 Если компилятору не хватает размера кучи и выдает [C1060](../../error-messages/compiler-errors-1/fatal-error-c1060.md) сообщение об ошибке при использовании **/Zm** параметр компилятора защищены слишком много памяти. Рассмотрите возможность удаления **/Zm** параметр. Если компилятор выдает [C1076](../../error-messages/compiler-errors-1/fatal-error-c1076.md) сообщение об ошибке, сопровождающие [C3859](../../error-messages/compiler-errors-2/compiler-error-c3859.md) сообщении указывается `factor` аргумент для использования при повторной компиляции с помощью **/Zm** параметр компилятора.  
  
 В следующей таблице показано влияние аргумента `factor` на предел выделения памяти в предположении, что размер буфера предварительно откомпилированных заголовков по умолчанию составляет 75 МБ.  
  
|Значение `factor`|Предел выделения памяти|  
|-----------------------|-----------------------------|  
|10|7.5 МБ|  
|100|75 МБ|  
|200|150 МБ|  
|1000|750 МБ|  
|2000|1500 МБ|  
  
## <a name="other-ways-to-set-the-memory-allocation-limit"></a>Другие способы установки предела выделения памяти  
  
#### <a name="to-set-the-zm-compiler-option-in-the-visual-studio-development-environment"></a>Установка параметра компилятора /Zm в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  В области навигации выберите **свойства конфигурации**, **C/C++**, **командной строки**.  
  
3.  Введите **/Zm** параметра компилятора в **Дополнительные параметры** поле.  
  
#### <a name="to-set-the-zm-compiler-option-programmatically"></a>Установка параметра компилятора /Zm программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)