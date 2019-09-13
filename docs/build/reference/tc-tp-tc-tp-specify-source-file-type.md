---
title: Параметры /Tc, /Tp, /TC, /TP (определение типа исходного файла)
ms.date: 01/11/2018
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
ms.openlocfilehash: c93da6d2498d46e4b7bf3ad37dde852bb6bc82a1
ms.sourcegitcommit: effb516760c0f956c6308eeded48851accc96b92
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70927629"
---
# <a name="tc-tp-tc-tp-specify-source-file-type"></a>Параметры /Tc, /Tp, /TC, /TP (определение типа исходного файла)

Параметр **/TC** указывает, что аргумент filename является исходным файлом C, даже если у него нет расширения c. Параметр **/TP** указывает, что аргумент filename является C++ исходным файлом, даже если у него нет расширения CPP или CXX. Пробел между параметром и именем файла является необязательным. Каждый параметр указывает один файл; чтобы указать дополнительные файлы, повторите эту команду.

**/TC** и **/TP** являются глобальными вариантами **/TC** и **/TP**. Они указывают компилятору обрабатывать все файлы, имена которых указаны в командной строке, как исходные файлы C ( **/TC**) C++ или исходные файлы ( **/TP**), без учета расположения в командной строке по отношению к параметру. Эти глобальные параметры можно переопределить для одного файла с помощью параметров **/TC** или **/TP**.

## <a name="syntax"></a>Синтаксис

> **/TC** _имя файла_ **/TP имя_файла**/TC/TP
>  
> 
> 

## <a name="arguments"></a>Аргументы

*filename*<br/>
Файл C или C++ с исходным кодом.

## <a name="remarks"></a>Примечания

По умолчанию **CL** предполагает, что файлы с расширением c имеют исходные файлы c и файлы с расширением CPP или CXX являются C++ исходными файлами.

Если указан параметр **TC** или **TC** , любая спецификация параметра [/Zc: wchar_t (wchar_t является собственным типом)](zc-wchar-t-wchar-t-is-native-type.md) игнорируется.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Выберите страницу свойств **Конфигурация** > **C/C++**  > **Дополнительно** .

1. Измените свойство **компилировать как** . Нажмите кнопку **ОК** или **Применить** , чтобы применить изменения.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CompileAs%2A>.

## <a name="examples"></a>Примеры

Эта командная строка CL указывает, что MAIN. c, TEST. ПРГ и COLLATE. ПРГ являются всеми исходными файлами C. CL не будет распознать PRINT. ПРГ.

> CL MAIN. Печать в/Тктест.ПРГ/Ткколлате.ПРГ. прг

Командная строка CL указывает, что TEST1. c, TEST2. CXX, TEST3., и TEST4. o компилируются как C++ файлы, а TEST5. z компилируется как файл c.

> CL TEST1. С TEST2. CXX TEST3. ДА, TEST4. O/TC TEST5. Z/TP

## <a name="see-also"></a>См. также

[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)
