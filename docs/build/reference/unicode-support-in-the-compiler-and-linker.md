---
title: "Поддержка Юникода в компиляторе и компоновщике | Документы Microsoft"
ms.custom: 
ms.date: 12/15/2017
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.UseUnicodeResponseFiles
- VC.Project.VCLibrarianTool.UseUnicodeResponseFiles
- VC.Project.VCCLCompilerTool.UseUnicodeResponseFiles
- VC.Project.VCXDCMakeTool.UseUnicodeResponseFiles
dev_langs:
- C++
helpviewer_keywords:
- Unicode, Visual C++
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fe775a53914089648a868a94aa2c863ee87790c5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="unicode-support-in-the-compiler-and-linker"></a>Поддержка Юникода в компиляторе и компоновщике

Большинство средств сборки Visual C++ поддерживает Юникод входов и выходов.

## <a name="filenames"></a>Имена файлов

Имена файлов, указанные в командной строке или в директивы компилятора (такие как `#include`) может содержать символы Юникода.

## <a name="source-code-files"></a>Файлы исходного кода

Символы Юникода поддерживаются в идентификаторах, макросах, строковых и символьных литералах и в комментариях.  Также поддерживаются универсальные имена символов.

Юникода могут быть введены в файл исходного кода в следующие кодировки:

- UTF-16 с прямым порядком байтов с или без отметки порядка байтов (BOM)

- UTF-16 с обратным порядком байтов с или без НЕЕ

- UTF-8 с BOM

## <a name="output"></a>Вывод

Во время компиляции компилятор выводит на консоль в кодировке UTF-16 диагностические сообщения.  Символы, которые могут отображаться на консоли зависят от свойств окна консоли.  Выходные данные компилятора перенаправлены в файл находится в текущей кодовой страницы ANSI консоли.

## <a name="linker-response-files-and-def-files"></a>Файлы ответов компоновщика и. DEF-файлы

Файлы ответа и DEF-файлы могут быть либо UTF-16 BOM или ANSI.

## <a name="asm-and-cod-dumps"></a>дампы на языке ассемблера и .cod

дампы на языке ассемблера и .cod находятся в ANSI по умолчанию для обеспечения совместимости с MASM. Используйте [параметр/FAu](../../build/reference/fa-fa-listing-file.md) для вывода UTF-8. Обратите внимание, что при указании **/FAs**, смешанный источник будет печататься напрямую и может выглядеть нечитаемыми, например, если исходный код — UTF-8, и вы не указали **/FAsu**.

## <a name="see-also"></a>См. также

[Создание кода C/C++ в командной строке](../../build/building-on-the-command-line.md)