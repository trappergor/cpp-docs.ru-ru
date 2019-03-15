---
title: Определения препроцессора (/D)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCNMakeTool.PreprocessorDefinitions
- VC.Project.VCCLCompilerTool.PreprocessorDefinitions
- /d
helpviewer_keywords:
- preprocessor definition symbols
- constants, defining
- macros, compiling
- /D compiler option [C++]
- -D compiler option [C++]
- D compiler option [C++]
ms.assetid: b53fdda7-8da1-474f-8811-ba7cdcc66dba
ms.openlocfilehash: 18bbdb980c63b3c04b432602afb2402c5e2c42e7
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57812087"
---
# <a name="d-preprocessor-definitions"></a>Определения препроцессора (/D)

Определяет символ предварительной обработки для исходного файла.

## <a name="syntax"></a>Синтаксис

```
/Dname[= | # [{string | number}] ]
```

## <a name="remarks"></a>Примечания

Этот символ можно использовать совместно с `#if` или `#ifdef` для условной компиляции исходного кода. Определение символа остается в силе до тех пор, пока он не будет переопределен в коде или его определение не будет отменено в коде с помощью директивы `#undef`.

**/D** имеет тот же эффект, что `#define` директиву в начало файла исходного кода, за исключением случаев, **/D** удаляет кавычки в командной строке и `#define` сохраняет их.

По умолчанию значение, связанное с символом, равно 1. Например **/D** `name` эквивалентен **/D**`name`**= 1**. В примере в конце этой статьи, определение **ТЕСТА** показано равным `1`.

Компиляция с помощью **/D** `name` **=** делает символ не имеет связанного значения. Хотя символа все равно можно использовать для условной компиляции кода, в остальных случаях использование символа будет бесполезным. В этом примере при компиляции с помощью **/DTEST =**, возникает ошибка. Это поведение напоминает использование `#define` со значением или без значения.

Эта команда определяет символ DEBUG в файле TEST.c:

**ТЕСТ /DDEBUG CL. C**

Эта команда удаляет все вхождения ключевого слова `__far` из файла TEST.c:

**CL /D__far=  TEST.C**

**CL** переменная среды не может быть присвоено строку, содержащую знак равенства. Чтобы использовать **/D** вместе с **CL** среды переменных, необходимо указать знак решетки вместо знака равенства:

```
SET CL=/DTEST#0
```

При определении символа предварительной обработки в командной строке необходимо учитывать правила синтаксического разбора компилятора и правила синтаксического разбора оболочки. Например, чтобы определить предварительной обработки символ процента (%) в программе укажите символы двух процента (%) в командной строке: Если указать только один, создается ошибка синтаксического анализа.

```
CL /DTEST=%% TEST.C
```

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Окна свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. В левой области выберите **свойства конфигурации**, **C/C++**, **препроцессор**.

1. В области справа в столбце справа **определения препроцессора** свойства, откройте раскрывающееся меню и выберите **изменить**.

1. В **определения препроцессора** диалоговом окне Добавить (по одному в строке), изменить или удалить одно или несколько определений. Выберите **ОК** для сохранения внесенных изменений.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.PreprocessorDefinitions%2A>.

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

[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)<br/>
[/U и /u (отмена определения символа)](u-u-undefine-symbols.md)<br/>
[Директива #undef (C/C++)](../../preprocessor/hash-undef-directive-c-cpp.md)<br/>
[Директива #define (C/C++)](../../preprocessor/hash-define-directive-c-cpp.md)
