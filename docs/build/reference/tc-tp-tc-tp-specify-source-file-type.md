---
title: Параметры /Tc, /Tp, /TC, /TP (определение типа исходного файла)
ms.date: 1/11/2018
f1_keywords:
- VC.Project.VCCLWCECompilerTool.CompileAs
- VC.Project.VCCLCompilerTool.CompileAs
- /Tp
- /tc
helpviewer_keywords:
- Tp compiler option [C++]
- /Tc compiler option [C++]
- -Tc compiler option [C++]
- source files, specifying to compiler
- Tc compiler option [C++]
- /Tp compiler option [C++]
- -Tp compiler option [C++]
ms.openlocfilehash: e435b48359a708408ff8659e53c9e7c4f7e80261
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50619119"
---
# <a name="tc-tp-tc-tp-specify-source-file-type"></a>Параметры /Tc, /Tp, /TC, /TP (определение типа исходного файла)

**/Tc** параметр указывает, что его аргумент filename является исходным файлом C, даже если он не имеет расширения c. **/Tp** параметр указывает, что его аргумент filename исходный файл C++, даже если он не имеет расширения .cpp или .cxx. Пробел между параметром и имя файла является необязательным. Каждый параметр определяет один файл; Чтобы указать дополнительные файлы, повторите параметр.

**/TC** и **/TP** представляют собой глобальные варианты **/Tc** и **/Tp**. Они указывают компилятору обрабатывать все файлы с именем в командной строке в виде исходных файлов C (**/TC**) или исходные файлы C++ (**/TP**), вне зависимости от расположения, в командной строке с параметром. Эти глобальные параметры можно переопределить на один файл с помощью параметра **/Tc** или **/Tp**.

## <a name="syntax"></a>Синтаксис

> **/TC** _filename_
>  **/Tp** _filename_
>  **/TC** 
>  **/TP**

## <a name="arguments"></a>Аргументы

*filename*<br/>
Исходный файл C или C++.

## <a name="remarks"></a>Примечания

По умолчанию **CL** предполагается, что файлы с расширением находятся исходные файлы C и файлов с помощью .cpp или .cxx расширения файлов исходного кода C++.

При любом **TC** или **Tc** параметр указан, Любая спецификация [/Zc: wchar_t (wchar_t — собственный тип)](../../build/reference/zc-wchar-t-wchar-t-is-native-type.md) параметр игнорируется.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **C/C++** > **Дополнительно** страницу свойств.

1. Изменить **компилировать как** свойство. Выберите **ОК** или **применить** для применения изменений.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CompileAs%2A>.

## <a name="examples"></a>Примеры

Эта командная строка CL указывает, что MAIN.c, TEST.prg и COLLATE.prg всех файлах исходного кода. CL не распознает PRINT.prg.

> CL MAIN. /TcCOLLATE.PRG /TcTEST.PRG C печати. PRG

Эта командная строка CL указывает, что TEST1.c, TEST2.cxx, TEST3.huh и TEST4.o компилируются как файлы C++ и TEST5.z компилируется как файл C.

> CL TEST1. C TEST2. CXX TEST3. ПРАВДА TEST4. O /Tc TEST5. Z /TP

## <a name="see-also"></a>См. также

[Параметры компилятора](../../build/reference/compiler-options.md)<br/>
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)
