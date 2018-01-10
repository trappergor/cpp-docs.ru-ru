---
title: "Директивы предварительной обработки файлов makefile | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- '!UNDEF'
- '!INCLUDE'
- '!IFNDEF'
- '!MESSAGE'
dev_langs: C++
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
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1bc73a86b0772b13731aaf7ac4e2ef0760caa8a5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="makefile-preprocessing-directives"></a>Директивы предварительной обработки файла makefile
Директивы предварительной обработки не учитывается регистр. Начальный восклицательный знак (!) должен находиться в начале строки. Ноль или более пробелов или вкладки могут отображаться после восклицания для отступа.  
  
 **! CMDSWITCHES**  
 {**+**&#124;  **-** }*параметр*... Каждый *параметр* включенный или off. Пробелы или знаки табуляции, должны предшествовать + или - оператор; ничего не должно быть между оператором и [параметр буквы](../build/nmake-options.md). Буквы не учитывается регистр и указаны без косая черта (/). Чтобы включить несколько параметров и выключить, используйте отдельные спецификации **! CMDSWITCHES**.  
  
 Только /D / I, / n и /S может использоваться в файле makefile. В файле Tools.ini, допустимы все параметры, за исключением /F, / Help, / nologo, / X, и /?. Изменения, указанные в блоке описания не вступают в силу до следующего блока описаний. Эта директива обновляет **MAKEFLAGS**; Если изменения наследуются рекурсии **MAKEFLAGS** указано.  
  
 **! Ошибка***текста*   
 Отображает *текст* ошибки U1050, затем останавливает NMAKE, даже if/k, / I, **. ИГНОРИРОВАТЬ**, **! CMDSWITCHES**, или использовать модификатор команды дефис (-). Пробелы или вкладки, прежде чем *текст* игнорируются.  
  
 **! СООБЩЕНИЕ***текста*   
 Отображает *текст* в стандартный вывод. Пробелы или вкладки, прежде чем *текст* игнорируются.  
  
 **! ВКЛЮЧИТЬ**[  **\<** ] *filename*[  **>** ]  
 Считывает *filename* как файла makefile, затем продолжает текущего файла makefile. NMAKE ищет *filename* сначала в каталоге указанной или текущей затем рекурсивно через директории любого родительские сборочных файлов проекта, затем, если *filename* заключено в угловые скобки (\<>), в каталогах, указанных в **INCLUDE** макросом, который изначально установлено значение переменной среды INCLUDE. Для передачи **. СУФФИКСЫ** параметры **. ЦЕННОЕ**и правила вывода для файлов makefile рекурсивной.  
  
 **! ЕСЛИ**  `constantexpression`  
 Обрабатывает операторы между **! Если** , а затем **! ELSE** или `!ENDIF` Если `constantexpression` имеет ненулевое значение.  
  
 **! IFDEF***имя макроса*   
 Обрабатывает операторы между `!IFDEF` , а затем **! ELSE** или `!ENDIF` Если *имя макроса* определен. Макрос null считается определен.  
  
 **! Ifndef:***имя макроса*   
 Обрабатывает операторы между **! Ifndef:** , а затем **! ELSE** или `!ENDIF` Если *имя макроса* не определен.  
  
 **! ELSE**[**IF** *constantexpression* &#124; **IFDEF** *имя макроса*&#124; **Ifndef:** *имя макроса*]  
 Обрабатывает операторы между **! ELSE** , а затем `!ENDIF` Если предварительного **! Если**, `!IFDEF`, или **! Ifndef:** инструкции, равно нулю. Необязательные ключевые слова позволяют управлять предварительной обработки.  
  
 **! ELSEIF**  
 Синоним для **! ELSE IF**.  
  
 **! ELSEIFDEF**  
 Синоним для **! ELSE IFDEF**.  
  
 **! ELSEIFNDEF**  
 Синоним для **! ELSE ifndef:**.  
  
 `!ENDIF`  
 Отмечает конец **! Если**, `!IFDEF`, или **! Ifndef:** блока. Любой текст после `!ENDIF` в той же строке учитывается.  
  
 **! UNDEF***имя макроса*   
 Отменяет определение *имя макроса*.  
  
## <a name="see-also"></a>См. также  
 [Предварительная обработка файла Makefile](../build/makefile-preprocessing.md)