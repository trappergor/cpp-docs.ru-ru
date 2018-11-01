---
title: C.2 Правила
ms.date: 11/04/2016
ms.assetid: 4d52fef7-3eb7-4480-a335-8ed48681092b
ms.openlocfilehash: 7c0de4c14e229716bcf764d9859be439090368b1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50642810"
---
# <a name="c2-rules"></a>C.2 Правила

Нотация описан в разделе 6.1 стандарта C. В этом приложении грамматики показано расширение для грамматики базовый язык для директивы OpenMP C и C++.

**/\* в C++ (ISO/IEC 14882:1998) \*/**

*оператор seq*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*statement*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*OpenMP директива*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*оператор seq инструкции*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*оператор seq openmp директива*

**/\* в C90 (ISO/IEC 9899: 1990) \*/**

*statement-list*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*statement*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*OpenMP директива*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*список операторов оператор*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*список операторов openmp директива*

**/\* в C99 (ISO/IEC 9899: 1999) \*/**

*блок item*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*declaration*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*statement*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*OpenMP директива*

**/\* стандартные инструкции \*/**

*statement*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Конструкция OpenMP*

*Конструкция OpenMP*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*параллельные конструкции*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*для конструкции*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Конструкция разделы*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Конструкция одного*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*параллельный для конструкции*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*параллельный разделы конструкция*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Конструкция master*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Конструкция Critical*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Конструкция atomic*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*упорядоченные конструкция*

*Директива OpenMP*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Барьер директива*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Flush директива*

*структурированный блок*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*statement*

*параллельные конструкции*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*структурированный блок параллельного директива*

*Директива параллельного*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**# Директива #pragma omp parallel** *параллельного предложение*<sub>optseq</sub> *новой строки*

*предложение параллельного*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Уникальный параллельного предложение*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*предложения данных*

*уникальное предложение параллельного*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Если (** *выражение* **)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**num_threads (** *выражение* **)**

*для конструкции*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*для директивы итерации оператор*

*для директивы*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**# Директива #pragma omp для** *предложении for*<sub>optseq</sub> *новой строки*

*для предложения*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Уникальный для предложения*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*предложения данных*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**nowait**

*Уникальный для предложения*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Упорядоченные**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**расписание (** *вид расписания* **)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**расписание (** *вид расписания* **,** *выражение* **)**

*Вид расписания*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**static**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**динамические**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Интерактивная**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Среда выполнения**

*Конструкция разделах*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*раздел области разделов директива*

*Директива разделах*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**# Директива #pragma omp разделах** *разделах предложение*<sub>optseq</sub> *новой строки*

*предложение разделах*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*предложения данных*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**nowait**

*область разделе*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*{разделе последовательность}*

*раздел последовательности*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*директивы Section*<sub>opt</sub> *структурированный блок*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*структурированные директивы section разделе последовательности блок*

*директивы Section*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Директива #pragma omp разделе** *новой строки*

*Конструкция одного*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*структурированный блок одной директивы*

*Директива одним*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**# Директива #pragma omp единый** *одним предложением*<sub>optseq</sub> *новой строки*

*одним предложением*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*предложения данных*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**nowait**

*параллельный для конструкции*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Инструкции итерации параллельного для директивы*

*параллельный для директивы*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**# Директива #pragma omp parallel для** *предложении for параллельного*<sub>optseq</sub> *новой строки*

*параллельный для предложения*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Уникальный параллельного предложение*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Уникальный для предложения*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*предложения данных*

*параллельных разделах конструкция*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*раздел области параллельной разделы директива*

*параллельных разделах директив*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**# Директива #pragma omp параллельных разделов** *параллельных разделах предложении*<sub>optseq</sub> *новой строки*

*параллельных разделах предложении*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Уникальный параллельного предложение*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*предложения данных*

*Конструкция master*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*структурированный блок master директива*

*master директива*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**# Директива #pragma omp master** *новой строки*

*Конструкция Critical*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*структурированный блок директивы Critical*

*директивы Critical*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**# Директива #pragma omp критических** *регион фраза*<sub>opt</sub> *новой строки*

*Регион фраза*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*(идентификатор)*

*Директива Barrier*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**barrier omp директивы pragma #** *новой строки*

*Конструкция atomic*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*оператор выражения директивы atomic*

*атомарная директива*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**# Директива #pragma omp atomic** *новой строки*

*Директива Flush*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**# Директива #pragma omp записи на диск** *переменных flush*<sub>opt</sub> *новой строки*

*Flush переменных*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*(переменная list)*

*упорядоченные конструкция*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*структурированный блок упорядоченные директива*

*упорядоченные директива*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Директива #pragma omp # упорядоченные** *новой строки*

**/\* Стандартные объявления \*/**

*declaration*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Директива threadprivate*

*Директива threadprivate*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**# Директива #pragma omp threadprivate (** *списка переменной***)** *новой строки*

*предложение Data*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**закрытый (** *списка переменной* **)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**copyprivate (***списка переменной***)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**firstprivate (***списка переменной***)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**lastprivate (** *списка переменной***)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Общие (** *списка переменной* **)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**по умолчанию (общий)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**по умолчанию (нет)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**сокращение (***оператором редукции***:***списка переменной***)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**copyin (***списка переменной***)**

*оператором редукции*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;Один из:  **+  \* -& ^ &#124; & &&#124;&#124;**

**/\* в C \*/**

*переменная list*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*identifier*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*переменная list* **,** *идентификатор*

**/\* в C++ \*/**

*переменная list*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*идентификатор выражение*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*переменная list* **,** *идентификатор выражения*