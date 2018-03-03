---
title: "-constexpr (вычислении constexpr управления) | Документы Microsoft"
ms.custom: 
ms.date: 08/15/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /constexpr
- -constexpr
dev_langs:
- C++
helpviewer_keywords:
- /constexpr control constexpr evaluation [C++]
- -constexpr control constexpr evaluation [C++]
- constexpr control constexpr evaluation [C++]
ms.assetid: 76d56784-f5ad-401d-841d-09d1059e8b8c
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7e594eb697c8972d28b513a3638d3eb704258b5e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="constexpr-control-constexpr-evaluation"></a>/constexpr (вычислении constexpr управления)  
  
Используйте **/constexpr** параметры компилятора, параметры управления `constexpr` оценки во время компиляции.  
  
## <a name="syntax"></a>Синтаксис  
  
> /constexpr:Depth*N*  
> /constexpr:backtrace*N*  
> /constexpr:Steps*N*  
  
## <a name="arguments"></a>Аргументы  
  
**Глубина***N*  
Ограничение глубины рекурсивной `constexpr` вызов к функции *N* уровней. Значение по умолчанию — 512.  
  
**backtrace***N*  
Показать до *N* `constexpr` оценок в диагностике. Значение по умолчанию — 10.  
  
**действия***N*  
Завершение `constexpr` оценки *N* действия. Значение по умолчанию — 100 000.  
  
## <a name="remarks"></a>Примечания  
  
**/Constexpr** управляют вычисление во время компиляции компилятор `constexpr` выражения. Этапы вычисления, уровней рекурсии и глубину backtrace являются контроле, чтобы запретить компилятору тратит слишком много времени на `constexpr` оценки. Дополнительные сведения о `constexpr` элемент языка. в разделе [constexpr (C++)](../../cpp/constexpr-cpp.md).  

**/Constexpr** параметры будут доступны, начиная с Visual Studio 2015.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1. Откройте свой проект **страницы свойств** диалоговое окно.   
  
2. В разделе **свойства конфигурации**, разверните **C/C++** папку и выберите **командной строки** страницу свойств.  
  
3. Введите любой **/constexpr** параметры компилятора в **Дополнительные параметры** поле. Выберите **ОК** или **применить** для сохранения изменений.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>См. также  
  
[Параметры компилятора](../../build/reference/compiler-options.md)   
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)