---
title: Переменные среды CL | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- cl
dev_langs:
- C++
helpviewer_keywords:
- INCLUDE environment variable
- cl.exe compiler, environment variables
- LIBPATH environment variable
- environment variables, CL compiler
ms.assetid: 2606585b-a681-42ee-986e-1c9a2da32108
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6f3986097bcb5028d9ad708c9a3132f5e417d502
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="cl-environment-variables"></a>Переменные среды CL

Средство CL использует следующие переменные среды:

- CL и \_CL\_, если определен. Средство CL добавляет параметры и аргументы, заданные в переменной среды компилятора CL аргументов командной строки и добавляет параметры и определенные аргументы в \_CL\_, перед обработкой.

- INCLUDE, которая должна указывать на подкаталог \include папки установки Visual C++.

- Переменная среды LIBPATH, которая указывает каталоги для поиска файлов метаданных для ссылки на [#using](../../preprocessor/hash-using-directive-cpp.md). Подробнее о переменной LIBPATH см. в статье `#using`.

Можно задать CL или \_CL\_ переменной среды, используя следующий синтаксис:

> ЗАДАТЬ CL = [[*параметр*]... [*файл*]...] [/ link *связи opt* ...]  
> ЗАДАТЬ \_CL\_= [[*параметр*]... [*файл*]...] [/ link *связи opt* ...]

Дополнительные сведения об аргументах для компилятора CL и \_CL\_ переменных среды в разделе [синтаксис командной строки компилятора](../../build/reference/compiler-command-line-syntax.md).

Эти переменные среды можно использовать для определения наиболее часто используемых файлов и параметров, а с помощью командной строки можно определить отдельные файлы и параметры для определенных целей. CL и \_CL\_ переменные среды не более 1024 символов (ограничение ввода командной строки).

Невозможно использовать параметр /D для определения символа, в который входит знак равенства (=). Символ номера (#) можно заменить на символ равенства. Таким образом, можно использовать CL или \_CL\_ переменных среды для определения констант препроцессора с явными значениями — например, `/DDEBUG#1` для определения `DEBUG=1`.

Дополнительные сведения см. в разделе [Установка переменных среды](../../build/setting-the-path-and-environment-variables-for-command-line-builds.md).

## <a name="examples"></a>Примеры

Ниже приведен пример настройки переменной среды компилятора CL:

> УСТАНОВИТЕ/Ox /I\INCLUDE\MYINCLS CL = Zp2 \LIB\BINMODE. OBJ

Если значение этой переменной среды, если ввести `CL INPUT.C` из командной строки, это команда:

> \LIB\BINMODE /I\INCLUDE\MYINCLS/Ox /Zp2 CL. OBJ ВХОДНЫЕ ДАННЫЕ. C

В следующем примере простая команда CL компилирует исходные файлы FILE1.c и FILE2.c, а затем компонует объектные файлы FILE1.obj, FILE2.obj и FILE3.obj:

> НАБОР CL = FILE1. C FILE2. C  
> ЗАДАТЬ \_CL\_= ФАЙЛ3. OBJ  
> CL  

Результаты аналогичны следующей команде:

> CL FILE1. C FILE2. ФАЙЛ3 C. OBJ

## <a name="see-also"></a>См. также

[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)   
[Параметры компилятора](../../build/reference/compiler-options.md)
