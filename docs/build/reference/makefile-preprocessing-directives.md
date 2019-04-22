---
title: Директивы предварительной обработки файла makefile
ms.date: 06/14/2018
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
ms.openlocfilehash: 0945d0e1c149b7e1ab31b0dbbd5003f8b15a1e4d
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57826783"
---
# <a name="makefile-preprocessing-directives"></a>Директивы предварительной обработки файла makefile

Директивы предварительной обработки не чувствительны к регистру. Начальный восклицательный знак (!) должны находиться в начале строки. Ноль или более пробелов или вкладки может отображаться после точки восклицательный знак для отступа.

- **!CMDSWITCHES** {**+** &#124; **-**}*option* ...

   Каждый *параметр* в списке или отключить. Пробелы или символы табуляции должен находиться перед + или - оператор; ничего не должно быть между оператором и [параметр буквы](nmake-options.md). Буквы не учитывается регистр и указаны без косая черта (/). Чтобы включить несколько параметров и выключить, используйте отдельные спецификации **! CMDSWITCHES**.

   Только /D / I, /N и /S может использоваться в файле makefile. В файле Tools.ini, допускаются все параметры, за исключением /F, / Help, / nologo, / X, и /?. Изменения, указанные в блоке описания не вступили в силу до следующего блока описаний. Эта директива обновляет **MAKEFLAGS**; Если изменения наследуются рекурсии **MAKEFLAGS** указан.

- **! Ошибка** *текста*

   Отображает *текст* в ошибки U1050, затем останавливает NMAKE, даже если /K, / I, **. ИГНОРИРОВАТЬ**, **! CMDSWITCHES**, или используется модификатор команды дефис (-). Пробелы или вкладки перед *текст* игнорируются.

- **! СООБЩЕНИЕ** *текста*

   Отображает *текст* в стандартный вывод. Пробелы или вкладки перед *текст* игнорируются.

- **! ВКЛЮЧИТЬ** [ **\<** ] *filename* [ **>** ]

   Считывает *filename* как файла makefile, затем продолжает операции текущий файл makefile. NMAKE ищет *filename* сначала в указанный или текущем каталоге, затем рекурсивно каталогах любого родительские файлы makefile, затем, если *filename* заключено в угловые скобки (\<>), в каталогах, указанных **INCLUDE** макросом, который изначально установлено значение переменной среды INCLUDE. Для передачи **. СУФФИКСЫ** параметры **. ЦЕННЫЕ**и правила вывода для файлов makefile рекурсивной.

- **! Если** *constant_expression*

   Обрабатывает операторы между **! Если** и следующей **! ELSE** или **! ENDIF** Если *constant_expression* имеет ненулевое значение.

- **! IFDEF** *имя макроса*

   Обрабатывает операторы между **! IFDEF** и следующей **! ELSE** или **! ENDIF** Если *имя макроса* определен. Макрос null считается должна определяться.

- **! IFNDEF** *имя макроса*

   Обрабатывает операторы между **! IFNDEF** и следующей **! ELSE** или **! ENDIF** Если *имя макроса* не определен.

- **! ELSE** [**IF** *constant_expression* &#124; **IFDEF** *имя макроса* &#124; **IFNDEF**  *имя макроса*]

   Обрабатывает операторы между **! ELSE** и следующей **! ENDIF** Если предварительного **! Если**, **! IFDEF**, или **! IFNDEF** инструкции, равно нулю. Необязательные ключевые слова позволяют управлять предварительной обработки.

- **! ELSEIF**

   Синоним для **! ELSE IF**.

- **! ELSEIFDEF**

   Синоним для **! ELSE IFDEF**.

- **! ELSEIFNDEF**

   Синоним для **! ELSE IFNDEF**.

- **! ENDIF**

   Помечает конец **! Если**, **! IFDEF**, или **! IFNDEF** блока. Любой текст после **! ENDIF** в той же строке учитывается.

- **! UNDEF** *имя макроса*

   Отменяет определение *имя макроса*.

## <a name="see-also"></a>См. также

- [Предварительная обработка файла Makefile](makefile-preprocessing.md)