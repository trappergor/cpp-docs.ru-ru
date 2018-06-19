---
title: -D (определения препроцессора) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCNMakeTool.PreprocessorDefinitions
- VC.Project.VCCLCompilerTool.PreprocessorDefinitions
- /d
dev_langs:
- C++
helpviewer_keywords:
- preprocessor definition symbols
- constants, defining
- macros, compiling
- /D compiler option [C++]
- -D compiler option [C++]
- D compiler option [C++]
ms.assetid: b53fdda7-8da1-474f-8811-ba7cdcc66dba
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4b8b386d55804421fb6cb454b4818db52e7cea85
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32376602"
---
# <a name="d-preprocessor-definitions"></a>Определения препроцессора (/D)
Определяет символ предварительной обработки для исходного файла.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/Dname[= | # [{string | number}] ]  
```  
  
## <a name="remarks"></a>Примечания  
 Этот символ можно использовать совместно с `#if` или `#ifdef` для условной компиляции исходного кода. Определение символа остается в силе до тех пор, пока он не будет переопределен в коде или его определение не будет отменено в коде с помощью директивы `#undef`.  
  
 **/D** действует так же, как `#define` директиву в начало файла исходного кода, за исключением того, что **/D** удаляет кавычки в командной строке и `#define` сохраняет их.  
  
 По умолчанию значение, связанное с символом, равно 1. Например **/D** `name` эквивалентно **/D**`name`**= 1**. В примере в конце данной статьи, определение **тест** показано равным `1`.  
  
 При компиляции с помощью **/D** `name` **=** делает символ не имеет связанного значения. Хотя символа все равно можно использовать для условной компиляции кода, в остальных случаях использование символа будет бесполезным. В этом примере при компиляции с помощью **/DTEST =**, возникает ошибка. Это поведение напоминает использование `#define` со значением или без значения.  
  
 Эта команда определяет символ DEBUG в файле TEST.c:  
  
 **ТЕСТ /DDEBUG CL. C**  
  
 Эта команда удаляет все вхождения ключевого слова `__far` из файла TEST.c:  
  
 **CL /D__far = TEST. C**  
  
 **CL** переменной окружения не может быть присвоено строку, содержащую знак равенства. Для использования **/D** вместе с **CL** среды переменной необходимо указать знак решетки вместо знака равенства:  
  
```  
SET CL=/DTEST#0  
```  
  
 При определении символа предварительной обработки в командной строке необходимо учитывать правила синтаксического разбора компилятора и правила синтаксического разбора оболочки. Например, чтобы определить в программе символ предварительной обработки в виде знака процентов (%), укажите в командной строке два знака процентов (%%): если указан только один знак, возникает ошибка синтаксического анализа.  
  
```  
CL /DTEST=%% TEST.C  
```  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Окна свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  В левой области выберите **свойства конфигурации**, **C/C++**, **препроцессор**.  
  
3.  В правой панели в правом столбце **определения препроцессора** свойства, откройте раскрывающееся меню и выберите **изменить**.  
  
4.  В **определения препроцессора** диалоговое окно, добавьте (по одному на строку), изменить или удалить одно или несколько определений. Выберите **ОК** для сохранения изменений.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.PreprocessorDefinitions%2A>.  
  
## <a name="example"></a>Пример  
  
```  
// cpp_D_compiler_option.cpp  
// compile with: /DTEST  
#include <stdio.h>  
  
int main( )  
{  
    #ifdef TEST  
        printf_s("TEST defined %d\n", TEST);  
    #else  
        printf_s("TEST not defined\n");  
    #endif  
}  
```  
  
```Output  
TEST defined 1  
```  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)   
 [/U и /u (Отмена определения символа)](../../build/reference/u-u-undefine-symbols.md)   
 [#undef директивы (C/C++)](../../preprocessor/hash-undef-directive-c-cpp.md)   
 [Директива #define (C/C++)](../../preprocessor/hash-define-directive-c-cpp.md)