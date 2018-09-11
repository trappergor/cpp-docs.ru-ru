---
title: -constexpr (управлять вычислением constexpr) | Документация Майкрософт
ms.custom: ''
ms.date: 08/15/2017
ms.technology:
- cpp-tools
ms.topic: reference
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
ms.workload:
- cplusplus
ms.openlocfilehash: 475702792686a3de8d1ae52bd9e40ef113c49da1
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43202578"
---
# <a name="constexpr-control-constexpr-evaluation"></a>/constexpr (управлять вычислением constexpr)  
  
Используйте **/constexpr** параметры компилятора, параметры управления **constexpr** оценки во время компиляции.  
  
## <a name="syntax"></a>Синтаксис  
  
> **/constexpr:Depth**<em>N</em>  
> **/constexpr:backtrace**<em>N</em>  
> **/constexpr:Steps**<em>N</em>  
  
## <a name="arguments"></a>Аргументы  
  
**Глубина**<em>N</em>  
Ограничение глубины рекурсивной **constexpr** вызов к функции *N* уровней. Значение по умолчанию — 512.  
  
**backtrace**<em>N</em>  
Показать до *N* **constexpr** оценок в системе диагностики. Значение по умолчанию — 10.  
  
**действия**<em>N</em>  
Завершить **constexpr** оценки после *N* действия. Значение по умолчанию равно 100 000.  
  
## <a name="remarks"></a>Примечания  
  
**/Constexpr** компилятора параметры управляют вычисление во время компиляции **constexpr** выражения. Чтобы запретить компилятору выполнять тратит слишком много времени на осуществляется по оценке продуктов, уровней рекурсии и глубина backtrace **constexpr** оценки. Дополнительные сведения о **constexpr** элемента языка, см. в разделе [constexpr (C++)](../../cpp/constexpr-cpp.md).  

**/Constexpr** параметры будут доступны, начиная с Visual Studio 2015.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1. Откройте свой проект **страницы свойств** диалоговое окно.   
  
2. В разделе **свойства конфигурации**, разверните **C/C++** папку и выберите **командной строки** страницу свойств.  
  
3. Введите любой **/constexpr** параметров компилятора в **Дополнительные параметры** поле. Выберите **ОК** или **применить** для сохранения изменений.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>См. также  
  
[Параметры компилятора](../../build/reference/compiler-options.md)   
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)