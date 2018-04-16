---
title: -Yc (создать предкомпилированный заголовочный файл) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.UsePrecompiledHeader
- /yc
- VC.Project.VCCLWCECompilerTool.PrecompiledHeaderThrough
- VC.Project.VCCLWCECompilerTool.UsePrecompiledHeader
- VC.Project.VCCLCompilerTool.PrecompiledHeaderThrough
dev_langs:
- C++
helpviewer_keywords:
- precompiled header files, creating
- PCH files, creating
- .pch files, creating
- -Yc compiler option [C++]
- /Yc compiler option [C++]
- Yc compiler option [C++]
ms.assetid: 47c2e555-b4f5-46e6-906e-ab5cf21f0678
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 865b5e0fa7039a0b60f524c2f13a367569757d92
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="yc-create-precompiled-header-file"></a>/Yc (создать предкомпилированный заголовочный файл)
Указывает компилятору на необходимость создания файла предкомпилированного заголовка (PCH), представляющий состояние компиляции в определенной точке.  
  
## <a name="syntax"></a>Синтаксис  
  
> __/Yc__
> __/Yc__*имя файла*  
  
  
## <a name="arguments"></a>Аргументы  
*filename*  
 Указывает файл заголовка (.h). Если этот аргумент используется, компилятор компилирует весь код, включая h-файл.  
  
## <a name="remarks"></a>Примечания  
 Когда **/Yc** указан без аргумента, компилятор компилирует весь код до конца базового исходного файла или до точки в базовом файле где [hdrstop](../../preprocessor/hdrstop.md) директива. Итоговый PCH-файл имеет такое же базовое имя как базовый исходный файл, если не указано имя другой файл с помощью **hdrstop** pragma или **/FP** параметр.  
  
 Предварительно скомпилированный код сохраняется в файле с именем, созданным из базового имени файла, заданного параметром **/Yc** параметр и с расширением PCH. Можно также использовать [/Fp (имя. PCH-файл)](../../build/reference/fp-name-dot-pch-file.md) параметр, чтобы указать имя файла предкомпилированного заголовка.  
  
 Если вы используете __/Yc__*filename*, компилятор компилирует весь код, включая указанный файл для последующего использования с [/Yu (использование предкомпилированного заголовка)](../../build/reference/yu-use-precompiled-header-file.md) параметр.  
  
 Если параметры __/Yc__*filename* и __/Yu__*filename* возникают в одной командной строке и обе ссылки или означает то же имя файла __/Yc__*filename* имеет более высокий приоритет. Эта функция упрощает создание файлов makefile.  
  
 Дополнительные сведения о предкомпилированных заголовках см. в разделе:  
  
-   [/Y (предварительно скомпилированные заголовки)](../../build/reference/y-precompiled-headers.md)  
  
-   [Создание предварительно скомпилированных файлов заголовков](../../build/reference/creating-precompiled-header-files.md)  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Выберите CPP-файл. CPP-файл должен #include в h-файл, содержащий сведения о предкомпилированных заголовках. Проект **/Yc** параметр может быть переопределено на уровне файла.  
  
2.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
3.  Откройте **свойства конфигурации**, **C/C++**, **предварительно скомпилированные заголовки** страницу свойств.  
  
4.  Изменить **предварительно скомпилированный заголовочный файл** свойство.  
  
5.  Чтобы задать имя файла, измените **файл предкомпилированного заголовка** свойство.
  
### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом  
  
-   См. разделы <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.PrecompiledHeaderThrough%2A> и <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UsePrecompiledHeader%2A>.  
  
## <a name="example"></a>Пример  
 Рассмотрим следующий код.  
  
```cpp  
// prog.cpp
// compile with: cl /c /Ycmyapp.h prog.cpp
#include <afxwin.h>   // Include header for class library  
#include "resource.h" // Include resource definitions  
#include "myapp.h"    // Include information specific to this app  
// ...  
```  
  
При компиляции этого кода с помощью команды `CL /YcMYAPP.H PROG.CPP`, компилятор сохраняет всю предварительную обработку для AFXWIN.h, RESOURCE.h и MYAPP.h в файл предкомпилированного заголовка с именем MYAPP.pch.  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md) [Создание файлов предкомпилированных заголовков](../../build/reference/creating-precompiled-header-files.md)