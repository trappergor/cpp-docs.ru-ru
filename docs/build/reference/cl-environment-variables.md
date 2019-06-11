---
title: Переменные среды CL
ms.date: 06/06/2019
f1_keywords:
- cl
helpviewer_keywords:
- INCLUDE environment variable
- cl.exe compiler, environment variables
- LIBPATH environment variable
- environment variables, CL compiler
ms.assetid: 2606585b-a681-42ee-986e-1c9a2da32108
ms.openlocfilehash: 0f7930728ef1bf6bea50c4388d52d30c569a8795
ms.sourcegitcommit: 8adabe177d557c74566c13145196c11cef5d10d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/10/2019
ms.locfileid: "66821531"
---
# <a name="cl-environment-variables"></a>Переменные среды CL

Средство CL использует следующие переменные среды:

- CL и \_CL_, если определено. Средство CL добавляет параметры и аргументы, заданные в переменной среды компилятора CL на аргументы командной строки и добавляет параметры и определить аргументы в \_CL_ перед обработкой.

- ВКЛЮЧИТЬ, которая должна указывать на подкаталог \include установку Visual Studio.

- LIBPATH, которая указывает каталоги для поиска файлов метаданных, на которые ссылается [#using](../../preprocessor/hash-using-directive-cpp.md). Дополнительные сведения о переменной LIBPATH см. в разделе [#using](../../preprocessor/hash-using-directive-cpp.md).

Можно задать компилятора CL или \_CL_ переменной среды, используя следующий синтаксис:

> ЗАДАЙТЕ CL = [[*параметр*]... [*файл*]...] [/ link *-opt ссылку* ...] \
> ЗАДАЙТЕ \_CL\_= [[*параметр*]... [*файл*]...] [/ link *-opt ссылку* ...]

Дополнительные сведения об аргументах для компилятора CL и \_CL_ переменные среды, см. в разделе [синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md).

Эти переменные среды можно использовать для определения файлов и параметров, наиболее часто. Затем используйте командную строку, чтобы предоставить дополнительные файлы и параметры к CL для определенных целей. CL и \_переменные среды CL_ ограничены до 1024 символов (ограничение ввода командной строки).

Нельзя использовать [/D](d-preprocessor-definitions.md) параметр, чтобы определить символ, который использует знак равенства ( **=** ). Вместо этого можно использовать знак номера ( **#** ) для знака равенства. Таким образом, можно использовать компилятора CL или \_CL_ переменных среды для определения констант препроцессора с явными значениями — например, `/DDEBUG#1` для определения `DEBUG=1`.

Дополнительные сведения см. в разделе [Настройка переменных среды](../setting-the-path-and-environment-variables-for-command-line-builds.md).

## <a name="examples"></a>Примеры

Команду ниже приведен пример настройки переменной среды компилятора CL.

> SET CL=/Zp2 /Ox /I\INCLUDE\MYINCLS \LIB\BINMODE.OBJ

Если значение переменной среды компилятора CL, если ввести `CL INPUT.C` в командной строке команда становится:

> CL /Zp2 /Ox /I\INCLUDE\MYINCLS \LIB\BINMODE.OBJ INPUT.C

В следующем примере простая команда CL компилирует исходные файлы FILE1.c и FILE2.c, а затем компонует объектные файлы FILE1.obj, FILE2.obj и FILE3.obj:

> SET CL=FILE1.C FILE2.C \
> SET \_CL_=FILE3.OBJ \
> CL

Эти переменные среды в вызове к CL имеют тот же эффект, что следующую команду:

> CL FILE1.C FILE2.C FILE3.OBJ

## <a name="see-also"></a>См. также

[Настройка параметров компилятора](compiler-command-line-syntax.md) \
[Параметры компилятора MSVC](compiler-options.md)
