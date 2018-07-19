---
title: -GX (Включить обработку исключений) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /gx
dev_langs:
- C++
helpviewer_keywords:
- exception handling, enabling
- /GX compiler option [C++]
- -GX compiler option [C++]
- cl.exe compiler, exception handling
- enable exception handling compiler option [C++]
- GX compiler option [C++]
ms.assetid: 933b43ba-de77-4ff8-a48b-7074de90bc1c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ee2d3d31a9f091e6aa3fbed39f702471047a01dd
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32376719"
---
# <a name="gx-enable-exception-handling"></a>/GX (включить обработку исключений)
Не рекомендуется. Включает синхронную обработку исключений с помощью в предположении, что функции, объявленные с помощью `extern "C"` не создают исключений.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/GX  
```  
  
## <a name="remarks"></a>Примечания  
 **/GX** является устаревшим. Использовать эквивалентные [/EHsc](../../build/reference/eh-exception-handling-model.md) вместо него. Список параметров компилятора см. в разделе **нерекомендуемые и удаленные параметры компилятора** статьи [параметры компилятора, упорядоченные по категориям](../../build/reference/compiler-options-listed-by-category.md).  
  
 По умолчанию **/EHsc**, эквивалентные **/GX**, действует при компиляции с помощью среды разработки Visual Studio. При использовании программы командной строки, обработка исключений не указан. Это эквивалентно **/GX-**.  
  
 Дополнительные сведения см. в разделе [обработку исключений C++](../../cpp/cpp-exception-handling.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  В области навигации выберите **свойства конфигурации**, **C/C++**, **командной строки**.  
  
3.  Введите параметр компилятора в поле **Дополнительные параметры** .  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)   
 [/EH (модель обработки исключений)](../../build/reference/eh-exception-handling-model.md)