---
title: Директивы предварительной обработки файла makefile
ms.date: 08/11/2019
f1_keywords:
- '!UNDEF'
- '!INCLUDE'
- '!IFNDEF'
- '!MESSAGE'
helpviewer_keywords:
- ERROR directive
- '!MESSAGE directive'
- IF directive
- '!UNDEF directive'
- IFDEF directive
- '!ELSEIF directive'
- '!IFDEF directive'
- '!IF directive'
- UNDEF directive
- '!CMDSWITCHES directive'
- ENDIF directive
- directives, makefile preprocessing
- INCLUDE directive
- IFNDEF directive
- preprocessing directives, makefiles
- '!IFNDEF directive'
- ELSEIFNDEF directive
- NMAKE program, expressions
- ELSEIF directive
- '!ERROR directive'
- '!ENDIF directive'
- MESSAGE directive
- '!INCLUDE directive'
- '!ELSEIFNDEF directive'
- CMDSWITCHES directive
- '!ELSEIFDEF directive'
- '!ELSE directive'
- NMAKE program, preprocessor directives
- makefiles, preprocessing directives
- ELSE directive
- ELSEIFDEF directive
ms.assetid: bcedeccb-d981-469d-b9e8-ab5d097fd8c2
ms.openlocfilehash: 4825ca180cb1b419a9ffa5232575ba1a24f8805d
ms.sourcegitcommit: db1ed91fa7451ade91c3fb76bc7a2b857f8a5eef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2019
ms.locfileid: "68980516"
---
# <a name="makefile-preprocessing-directives"></a>Директивы предварительной обработки файла makefile

Директивы предварительной обработки не учитывают регистр. Начальная восклицательная точка (!) должна находиться в начале строки. Ноль или более пробелов или символов табуляции могут появляться после восклицательного знака для отступов.

- `!CMDSWITCHES`{`+` &#124; } параметр... `-`

   Включает или выключает каждый *параметр* в списке. Пробелы или символы табуляции должны `+` находиться `-` перед оператором OR; между оператором и [буквами параметров](running-nmake.md#nmake-options)не может быть ни одного оператора. Буквы не учитывают регистр и задаются без косой черты (`/`). Чтобы включить некоторые параметры и отключить другие, используйте отдельные спецификации `!CMDSWITCHES`.

   В файле Makefile можно использовать только/D,/I,/N и/S. В файле Tools. ini разрешены все параметры, кроме/F,/HELP,/NOLOGO,/X и/?. Изменения, указанные в блоке описания, вступают в силу только после следующего блока описания. Эта директива обновляет **макефлагс**; изменения наследуются при рекурсии, если указан **макефлагс** .

- `!ERROR`*текстовая надпись*

   Отображает *текст* в ошибке NMAKE U1050, а затем останавливает NMAKE, даже если используется модификатор команды `.IGNORE`/k `!CMDSWITCHES`,/i,, или`-`тире (). Пробелы или символы табуляции перед *текстом* игнорируются.

- `!MESSAGE`*текстовая надпись*

   Отображает *текст* для стандартного вывода. Пробелы или символы табуляции перед *текстом* игнорируются.

- `!INCLUDE`[ `<` ] *имя_файла* [ `>` ]

   Считывает *filename* как файл makefile, а затем переходит к текущему файлу Makefile. NMAKE сначала ищет *filename* в указанном или текущем каталоге, а затем рекурсивно через каталоги любых родительских файлов makefile, а затем, если *filename* заключено в угловые скобки`< >`(), в каталогах, заданных параметром  **ВКЛЮЧИТЬ** макрос, изначально заданный для переменной среды include. Полезен для `.SUFFIXES` передачи параметров `.PRECIOUS`, и правил вывода в рекурсивные файлы Makefile.

- `!IF`*constant_expression*

   Обрабатывает операторы между `!IF` и следующим `!ELSE` или `!ENDIF` если *constant_expression* возвращает ненулевое значение.

- `!IFDEF`*имяМакроса*

   Обрабатывает операторы между `!IFDEF` и следующим `!ELSE` или `!ENDIF` , если определено *имяМакроса* . Считается, что определен пустой макрос.

- `!IFNDEF`*имяМакроса*

   Обрабатывает операторы между `!IFNDEF` и Next `!ELSE` или `!ENDIF` , если *макрос* не определен.

- `!ELSE`[`IF` constant_expression &#124; &#124; `IFDEF` `IFNDEF`

   Обрабатывает операторы между `!ELSE` и следующим `!ENDIF` , если предыдущие `!IF`инструкции, `!IFDEF`или `!IFNDEF` вычислены до нуля. Необязательные ключевые слова обеспечивают дальнейшее управление предварительной обработкой.

- `!ELSEIF`

   Является синонимом элемента `!ELSE IF`

- `!ELSEIFDEF`

   Является синонимом элемента `!ELSE IFDEF`

- `!ELSEIFNDEF`

   Является синонимом элемента `!ELSE IFNDEF`

- `!ENDIF`

   Помечает конец `!IF`блока, `!IFDEF`или `!IFNDEF` . Любой текст `!ENDIF` , напускаемый в той же строке, игнорируется.

- `!UNDEF`*имяМакроса*

   Отменяет определение *имяМакроса*.

## <a name="see-also"></a>См. также

- [Предварительная обработка файла Makefile](makefile-preprocessing.md)