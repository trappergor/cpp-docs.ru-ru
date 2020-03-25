---
title: Поддержка Юникода в компиляторе и компоновщике
ms.date: 12/15/2017
f1_keywords:
- VC.Project.VCLinkerTool.UseUnicodeResponseFiles
- VC.Project.VCLibrarianTool.UseUnicodeResponseFiles
- VC.Project.VCCLCompilerTool.UseUnicodeResponseFiles
- VC.Project.VCXDCMakeTool.UseUnicodeResponseFiles
helpviewer_keywords:
- Unicode, Visual C++
ms.openlocfilehash: 420b01263320cf86df3f99da4523cc2b8bb4d4b6
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80168841"
---
# <a name="unicode-support-in-the-compiler-and-linker"></a>Поддержка Юникода в компиляторе и компоновщике

Большинство средств C++ визуальной сборки поддерживают входные и выходные данные в Юникоде.

## <a name="filenames"></a>Имена файлов

Имена файлов, указанные в командной строке или в директивах компилятора (например, `#include`), могут содержать символы Юникода.

## <a name="source-code-files"></a>Файлы исходного кода

Символы Юникода поддерживаются в идентификаторах, макросах, строковых и символьных литералах и в комментариях.  Также поддерживаются универсальные имена символов.

Юникод может быть введен в файл исходного кода в следующих кодировках:

- UTF-16 с прямым порядком байтов со знаком или без метки порядка байтов (BOM)

- UTF-16 с обратным порядком байтов с BOM или без него

- UTF-8 with BOM

## <a name="output"></a>Выходные данные

Во время компиляции компилятор выводит диагностические данные в консоль в кодировке UTF-16.  Символы, которые могут отображаться в консоли, зависят от свойств окна консоли.  Выходные данные компилятора, перенаправляемые в файл, находятся в текущей кодовой странице консоли ANSI.

## <a name="linker-response-files-and-def-files"></a>Файлы ответов компоновщика и. DEF файлы

Файлы ответов и DEF-файлы могут быть в кодировке UTF – 16 с помощью спецификации или ANSI.

## <a name="asm-and-cod-dumps"></a>дампы ASM и. наложенные файлы

файлы дампов ASM и. наложены в ANSI по умолчанию для совместимости с MASM. Используйте [/Фау](fa-fa-listing-file.md) для вывода UTF-8. Обратите внимание, что при указании **/FAS**источник запутанной будет просто напечатан и может выглядеть неискаженным, например, если исходный код — UTF-8, а вы не указали **/ФАСУ**.

## <a name="see-also"></a>См. также раздел

[Использование набора средств MSVC из командной строки](../building-on-the-command-line.md)
