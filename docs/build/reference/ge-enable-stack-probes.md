---
title: -Ge (включить проверку стека) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /ge
dev_langs:
- C++
helpviewer_keywords:
- -Ge compiler option [C++]
- enable stack probes
- /Ge compiler option [C++]
- stack, stack probes
- stack probes
- stack checking calls
- Ge compiler option [C++]
ms.assetid: 4b54deae-4e3c-4bfa-95f3-ba23590f7258
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ce8b049426eb403e4bc41e842fe1ff2db1617dfc
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ge-enable-stack-probes"></a>/Ge (включить проверку стека)
Включает стековые зонды для каждого вызова функции, для которой требуется хранилище для локальных переменных.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/Ge  
```  
  
## <a name="remarks"></a>Примечания  
 Этот механизм полезен, если перезаписи функций проверки стека. Рекомендуется использовать [/Gh (включить _penter функция-ловушка)](../../build/reference/gh-enable-penter-hook-function.md) вместо перезаписи проверки стека.  
  
 [/GS (управления стек проверки вызовов)](../../build/reference/gs-control-stack-checking-calls.md) имеет тот же эффект.  
  
 **/GE** является устаревшим; начиная с Visual Studio 2005, компилятор автоматически создает проверка стека. Список параметров компилятора см. в разделе **нерекомендуемые и удаленные параметры компилятора** в [параметры компилятора, упорядоченные по категориям](../../build/reference/compiler-options-listed-by-category.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Откройте папку **C/C++** .  
  
3.  Выберите страницу свойств **Командная строка** .  
  
4.  Введите параметр компилятора в поле **Дополнительные параметры** .  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)