---
title: В. Грамматика OpenMP C и C++
ms.date: 01/16/2019
ms.assetid: 97a878ce-1533-47f7-a134-66fcbff48524
ms.openlocfilehash: 85e18161079b49e83cc9fedb3184ee220c889e75
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62362950"
---
# <a name="c-openmp-c-and-c-grammar"></a>В. Грамматика OpenMP C и C++

[C.1 Нотация](#c1-notation)<br/>
[C.2 Правила](#c2-rules)

## <a name="c1-notation"></a>C.1 Нотация

Грамматические правила состоят из имени для нетерминального, за которым следует двоеточие, следуют альтернативные варианты замены в отдельных строках.

Термин синтаксические выражения<sub>opt</sub> указывает, что термин не является обязательным в замены.

Синтаксические выражения *термин*<sub>optseq</sub> эквивалентен *термин seq*<sub>opt</sub> с следующие дополнительные правила:

*Термин seq*:  
&nbsp;&nbsp;&nbsp;&nbsp;*Термин*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Термин seq* *термин*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*term-seq*   `,` *term*

## <a name="c2-rules"></a>C.2 Правила

Нотация описан в разделе 6.1 стандарта C. В этом приложении грамматики показано расширение для грамматики базовый язык для директивы OpenMP C и C++.

**/\* в C++ (ISO/IEC 14882:1998) \*/**

*оператор seq*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*statement*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*OpenMP директива*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*statement-seq statement*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*statement-seq openmp-directive*

**/\* в C90 (ISO/IEC 9899: 1990) \*/**

*statement-list*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*statement*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*OpenMP директива*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*список операторов оператор*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*statement-list openmp-directive*

**/\* в C99 (ISO/IEC 9899: 1999) \*/**

*block-item*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*declaration*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*statement*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*OpenMP директива*

**/\* стандартные инструкции \*/**

*statement*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*openmp-construct*

*Конструкция OpenMP*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*parallel-construct*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*для конструкции*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sections-construct*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Конструкция одного*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*parallel-for-construct*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*parallel-sections-construct*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Конструкция master*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Конструкция Critical*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Конструкция atomic*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*упорядоченные конструкция*

*Директива OpenMP*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Барьер директива*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Flush директива*

*структурированный блок*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*statement*

*parallel-construct*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*parallel-directive structured-block*

*Директива параллельного*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp parallel` *parallel-clause*<sub>optseq</sub> *new-line*

*предложение параллельного*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Уникальный параллельного предложение*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*предложения данных*

*уникальное предложение параллельного*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `if (` *expression*   `)`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `num_threads (` *expression*   `)`

*для конструкции*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*для директивы итерации оператор*

*для директивы*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp for` *for-clause*<sub>optseq</sub> *new-line*

*для предложения*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Уникальный для предложения*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*предложения данных*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `nowait`

*Уникальный для предложения*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `ordered`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `schedule (` *Вид расписания*   `)`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `schedule (` *schedule-kind*   `,` *expression*   `)`

*Вид расписания*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `static`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `dynamic`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `guided`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `runtime`

*sections-construct*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*раздел области разделов директива*

*Директива разделах*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp sections` *sections-clause*<sub>optseq</sub> *new-line*

*предложение разделах*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*предложения данных*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `nowait`

*область разделе*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*{разделе последовательность}*

*раздел последовательности*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*section-directive*<sub>opt</sub> *structured-block*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*section-sequence section-directive structured-block*

*директивы Section*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp section` *new-line*

*Конструкция одного*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*структурированный блок одной директивы*

*Директива одним*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp single` *single-clause*<sub>optseq</sub> *new-line*

*одним предложением*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*предложения данных*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `nowait`

*parallel-for-construct*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Инструкции итерации параллельного для директивы*

*parallel-for-directive*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp parallel for` *parallel-for-clause*<sub>optseq</sub> *new-line*

*параллельный для предложения*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Уникальный параллельного предложение*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Уникальный для предложения*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*предложения данных*

*parallel-sections-construct*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*раздел области параллельной разделы директива*

*parallel-sections-directive*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp parallel sections` *parallel-sections-clause*<sub>optseq</sub> *new-line*

*parallel-sections-clause*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Уникальный параллельного предложение*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*предложения данных*

*Конструкция master*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*структурированный блок master директива*

*master директива*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp master` *new-line*

*Конструкция Critical*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*структурированный блок директивы Critical*

*директивы Critical*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp critical` *Регион фраза*<sub>opt</sub> *новой строки*

*Регион фраза*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*(идентификатор)*

*Директива Barrier*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp barrier` *new-line*

*Конструкция atomic*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*оператор выражения директивы atomic*

*атомарная директива*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp atomic` *new-line*

*Директива Flush*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp flush` *flush-vars*<sub>opt</sub> *new-line*

*Flush переменных*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*(переменная list)*

*упорядоченные конструкция*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*структурированный блок упорядоченные директива*

*упорядоченные директива*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp ordered` *new-line*

**/\* Стандартные объявления \*/**

*declaration*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Директива threadprivate*

*Директива threadprivate*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `# pragma omp threadprivate (` *variable-list*    `)` *new-line*

*предложение Data*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `private (` *variable-list*   `)`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `copyprivate (`  *variable-list*    `)`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `firstprivate (`  *variable-list*    `)`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `lastprivate (` *variable-list*    `)`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `shared (` *variable-list*   `)`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `default ( shared )`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `default ( none )`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `reduction (`  *оператором редукции*`:`*переменной list*    `)`<br/>
&nbsp;&nbsp;&nbsp;&nbsp;  `copyin (`  *variable-list*    `)`

*оператором редукции*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;Один из:   `+ \* - & ^ | && ||`

**/\* в C \*/**

*переменная list*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*identifier*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*variable-list*   `,` *identifier*

**/\* в C++ \*/**

*переменная list*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*id-expression*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*variable-list*   `,` *id-expression*
