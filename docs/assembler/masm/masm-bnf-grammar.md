---
title: Грамматика BNF Microsoft Macro Assembler
description: BNF описание MASM для x64.
ms.date: 12/17/2019
helpviewer_keywords:
- MASM (Microsoft Macro Assembler), BNF reference
ms.openlocfilehash: 29eae0b110f99f1f417e153f18aa2ac3aff5c69b
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2019
ms.locfileid: "75322826"
---
# <a name="microsoft-macro-assembler-bnf-grammar"></a>Грамматика BNF Microsoft Macro Assembler

На этой странице содержится BNF Описание грамматики MASM. Он предоставляется в качестве дополнения к справочным разделам и не гарантируется. Дополнительные сведения о ключевых словах, параметрах, операциях и т. д. см. в справочных материалах.

Чтобы проиллюстрировать использование BNF, на следующей схеме показано определение директивы TYPEDEF, начиная с нетерминального *типедефдир*.

![Пример MASM BNF](media/bnf.png)

Записи в каждой горизонтальной фигурной скобке — это терминалы (например, **NEAR16**, **NEAR32**, **FAR16**и **FAR32**) или Нетерминальные (такие как *квалификатор*, *куалифиедтипе*, *Distance*и *протоспек*), которые могут быть определены в дальнейшем. Каждое курсивное значение, нетерминальное в определении *типедефдир* , также является записью в BNF. Три точки по вертикали обозначают определение ветвления для нетерминального, которое, по простоте, не проиллюстрировано.

Грамматика BNF допускает рекурсивные определения. Например, грамматика использует Куалифиедтипе как возможное определение для Куалифиедтипе, которое также является компонентом определения квалификатора. Символ "|" указывает выбор между альтернативными выражениями, например *ендофлине* | *комментария*. Двойные фигурные скобки указывают необязательный параметр, например ⟦ *макропармлист* ⟧. Квадратные скобки фактически не отображаются в исходном коде.

## <a name="masm-nonterminals"></a>Нетерминальные программы MASM

*;;* \
&nbsp;&nbsp;&nbsp;&nbsp;*ендофлине* | *Комментарий*

*= Dir*\
&nbsp;&nbsp;&nbsp;&nbsp;*id* = *иммекспр* ;;

*аддоп*\
&nbsp;&nbsp;&nbsp;&nbsp;+ | -

*аекспр*\
&nbsp;&nbsp;&nbsp;&nbsp;*термин* | *аекспр* && *термин*

*алтид*\
&nbsp;&nbsp;&nbsp;&nbsp;*ID*

*арбитраритекст*\
&nbsp;&nbsp;&nbsp;&nbsp;*charlist*

*асминструктион*\
&nbsp;&nbsp;&nbsp;&nbsp;*мнемоника* ⟦ *експрлист* ⟧

*ассумедир*\
&nbsp;&nbsp;&nbsp;&nbsp;**предполагается** *ассумелист* ;; \
&nbsp;&nbsp;&nbsp;&nbsp;| **не предполагает ничего** ;;

*ассумелист*\
&nbsp;&nbsp;&nbsp;&nbsp;*ассумерегистер* | *ассумелист* , *ассумерегистер*\

*ассумерег*\
&nbsp;&nbsp;&nbsp;&nbsp;*Register* : *ассумевал*

*ассумерегистер*\
&nbsp;&nbsp;&nbsp;&nbsp;*ассумесегрег* | *ассумерег*

*ассумесегрег*\
&nbsp;&nbsp;&nbsp;&nbsp;*сегментрегистер* : *ассумесегвал*

*ассумесегвал*\
&nbsp;&nbsp;&nbsp;&nbsp;*фрамикспр* | **Nothing** | **Error**

*ассумевал*\
&nbsp;&nbsp;&nbsp;&nbsp;*куалифиедтипе* | **Nothing** | **Error**

*бкдконст*\
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *Sign* ⟧ *декнумбер*

*бинарйоп*\
&nbsp;&nbsp;&nbsp;&nbsp;= = |! = | > = | < = | > | < | &

*битдеф*\
&nbsp;&nbsp;&nbsp;&nbsp;*битфиелдид* : *Битфиелдсизе* ⟦ = *constExpr* ⟧

*битдефлист*\
&nbsp;&nbsp;&nbsp;&nbsp;*битдеф* | *битдефлист* , ⟦;; ⟧ *битдеф*

*битфиелдид*\
&nbsp;&nbsp;&nbsp;&nbsp;*ID*

*битфиелдсизе*\
&nbsp;&nbsp;&nbsp;&nbsp;*constExpr*

*блоккстатементс*\
&nbsp;&nbsp;&nbsp;&nbsp;*директивелист*\
&nbsp;&nbsp;&nbsp;&nbsp;|  **. ПРОДОЛЖИТЬ** **. Если** *цекспр* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;|  **. Прервать** ⟦ **. Если** *цекспр* ⟧

*bool*\
&nbsp;&nbsp;&nbsp;&nbsp;**TRUE** | **false**

*битерегистер*\
&nbsp;&nbsp;&nbsp;&nbsp;AL | AH | CL | CH | DL | DH | BL | BH | R8B | R9B | R10B | R11B | R12B | R13B | R14B | R15B

*цекспр*\
&nbsp;&nbsp;&nbsp;&nbsp;*аекспр* | *цекспр* || *аекспр*

*символьная*\
&nbsp;&nbsp;&nbsp;&nbsp;любой символ с порядковым номером в диапазоне от 0 до 255, кроме перевода строки (10).

\ *charlist*
&nbsp;&nbsp;&nbsp;&nbsp;*символ* | *charlist*

*className*\
&nbsp;&nbsp;&nbsp;&nbsp;*строки*

*коммдекл*\
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *неарфар* ⟧ ⟦ *лангтипе* ⟧ *ID* : *коммтипе*\
&nbsp;&nbsp;&nbsp;&nbsp;⟦: *constExpr* ⟧

*коммдир*\
&nbsp;&nbsp; **&nbsp;&nbsp;связи**\
&nbsp;&nbsp;&nbsp;&nbsp;*коммлист* ;;

\ *комментариев*
&nbsp;&nbsp;&nbsp;&nbsp;; *текст* ;;

*комментдир*\
&nbsp;&nbsp;&nbsp;разделитель **комментариев** &nbsp;\
&nbsp;&nbsp;&nbsp;&nbsp;*text*\
&nbsp;&nbsp;&nbsp;&nbsp; *текст* разделителя текста;;

*коммлист*\
&nbsp;&nbsp;&nbsp;&nbsp;*коммдекл* | *коммлист* , *коммдекл*

*коммтипе*\
&nbsp;&nbsp;&nbsp;&nbsp;*типа* | *constExpr*

*константные*\
&nbsp;&nbsp;&nbsp;&nbsp;*digits* ⟦ *радиксоверриде* ⟧

\ *constExpr*
&nbsp;&nbsp;&nbsp;&nbsp;*expr*

*контекстдир*\
&nbsp;&nbsp;&nbsp;&nbsp;**пушконтекст** *контекститемлист* ;; \
&nbsp;&nbsp;&nbsp;&nbsp;**попконтекст** *контекститемлист* ;;

*контекститем*\
&nbsp;&nbsp;&nbsp;&nbsp;**предполагает** | системы **счисления** | **список** | **ЦП** | **все**

*контекститемлист*\
&nbsp;&nbsp;&nbsp;&nbsp;*контекститем* | *контекститемлист* , *контекститем*

*контролблокк*\
&nbsp;&nbsp;&nbsp;&nbsp;*вхилеблокк* | *репеатблокк*

*контролдир*\
&nbsp;&nbsp;&nbsp;&nbsp;*контролиф* | *контролблокк*

*контролелсеиф*\
&nbsp;&nbsp;&nbsp;&nbsp; **. ELSEIF** &nbsp;&nbsp;&nbsp;&nbsp;*цекспр* ;; \
&nbsp;&nbsp;&nbsp;&nbsp;*директивелист* \
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *контролелсеиф* ⟧

*контролиф*\
&nbsp;&nbsp;&nbsp;&nbsp; **. Если** &nbsp;&nbsp;&nbsp;&nbsp;*цекспр* ;; \
&nbsp;&nbsp;&nbsp;&nbsp;*директивелист*\
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *контролелсеиф* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;⟦ **. ELSE** ;; \
&nbsp;&nbsp;&nbsp;&nbsp;[*директивелист*⟧ \
&nbsp;&nbsp;&nbsp;&nbsp; **. ENDIF** ;;

\ *сопроцессора*
&nbsp;&nbsp;&nbsp;&nbsp;. 8087 |. 287 |. 387 |. NO87

*крефдир*\
&nbsp;&nbsp;&nbsp;&nbsp;*крефоптион* ;;

*крефоптион*\
&nbsp;&nbsp;&nbsp;&nbsp; **. CREF**\
&nbsp;&nbsp;&nbsp;&nbsp;|  **. КСКРЕФ** ⟦ *idList* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;|  **. НОКРЕФ** ⟦ *idList* ⟧

*кксзекспр*\
&nbsp;&nbsp;&nbsp;&nbsp;*expr*\
&nbsp;&nbsp;&nbsp;&nbsp;|! *выражение*\
&nbsp;&nbsp;&nbsp;&nbsp;| *expr* = = expr \
&nbsp;&nbsp;&nbsp;&nbsp;| *expr* ! = expr

*датадекл*\
&nbsp;&nbsp;&nbsp;&nbsp;DB | ХРАНИЛИЩЕ ДАННЫХ | ДД | DF | DQ | DT | *тип данных* | *typeId*

*dataDir*\
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *ИД* ⟧ *;;*

\ *DataItem*
&nbsp;&nbsp;&nbsp;&nbsp;*датадекл* *скаларинстлист*\
&nbsp;&nbsp;&nbsp;&nbsp;| *структтаг* *структинстлист*\
&nbsp;&nbsp;&nbsp;&nbsp;| *typeId* *структинстлист*\
&nbsp;&nbsp;&nbsp;&nbsp;| *унионтаг* *структинстлист*\
&nbsp;&nbsp;&nbsp;&nbsp;| *рекордтаг* *рекординстлист*

\ *DataType*
&nbsp;&nbsp;&nbsp;&nbsp;байт | SBYTE | WORD | ТЕХНОЛОГИЙ | DWORD | СДВОРД | ФВОРД | QWORD | СКВОРД | ТБИТЕ | ОВОРД | REAL4 | REAL8 | REAL10 | ММВОРД | КСММВОРД | иммворд

*декдигит*\
&nbsp;&nbsp;&nbsp;&nbsp;0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 8

*декнумбер*\
&nbsp;&nbsp;&nbsp;&nbsp;*декдигит*\
&nbsp;&nbsp;&nbsp;&nbsp;| *декнумбер* *декдигит*

*разделитель*\
&nbsp;&nbsp;&nbsp;&nbsp;любой символ, кроме *вхитеспацечарактер*

*цифры*\
&nbsp;&nbsp;&nbsp;&nbsp;*декдигит*\
&nbsp;&nbsp;&nbsp;&nbsp;| *digits* *декдигит*\
&nbsp;&nbsp;&nbsp;&nbsp;| *digits* хексдигит

\ *директив*
&nbsp;&nbsp;&nbsp;&nbsp;*женералдир* | *сегментдеф*

*директивелист*\
&nbsp;&nbsp;&nbsp;*директива* &nbsp; | *директива* *директивелист*

*расстояние*\
&nbsp;&nbsp;&nbsp;&nbsp;*неарфар* | **NEAR16** | **NEAR32** | **FAR16** | **FAR32**

*e01*\
&nbsp;&nbsp;&nbsp;&nbsp;E01 *Ороп* *E02* | *E02*

*e02*\
&nbsp;&nbsp;&nbsp;&nbsp;E02 **и** *E03* | *E03*

*e03*\
&nbsp;&nbsp; **&nbsp;&nbsp;** *E04* | *E04*

*e04*\
&nbsp;&nbsp;&nbsp;&nbsp;*E04* *relOp* *E05* | *E05*

*e05*\
&nbsp;&nbsp;&nbsp;&nbsp;*E05* *аддоп* *E06* | *E06*

*e06*\
&nbsp;&nbsp;&nbsp;&nbsp;*E06* *мулоп* *e07* | *E06* *шифтоп* *E07* | *E07*

*e07*\
&nbsp;&nbsp;&nbsp;&nbsp;*E07* *аддоп* *E08* | *E08*

*e08*\
&nbsp;&nbsp;&nbsp;&nbsp;**High** *E09*\
&nbsp;&nbsp;&nbsp;&nbsp;| **Low** *E09*\
&nbsp;&nbsp;&nbsp;&nbsp;| **HIGHWORD** *E09*\
&nbsp;&nbsp;&nbsp;&nbsp;| **LOWWORD** *E09*\
&nbsp;&nbsp;&nbsp;&nbsp;| *E09*

*e09*\
&nbsp;&nbsp;&nbsp;&nbsp;**offset** *E10*\
&nbsp;&nbsp;&nbsp;&nbsp;| **SEG** *E10*\
&nbsp;&nbsp;&nbsp;&nbsp;| **лроффсет** *E10*\
&nbsp;&nbsp;&nbsp;&nbsp;| **типа** *E10*\
&nbsp;&nbsp;&nbsp;&nbsp;| **этой** *E10*\
&nbsp;&nbsp;&nbsp;&nbsp;| *E09* **ptr** *E10*\
&nbsp;&nbsp;&nbsp;&nbsp;| *E09* : *E10*\
&nbsp;&nbsp;&nbsp;&nbsp;| *E10*

*e10*\
&nbsp;&nbsp;&nbsp;&nbsp;*E10* . *e11*\
&nbsp;&nbsp;&nbsp;&nbsp;| *E10* ⟦ *expr* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;| *E11*

*e11*\
&nbsp;&nbsp;&nbsp;&nbsp;( *expr* ) \
&nbsp;&nbsp;&nbsp;&nbsp;| ⟦ *expr* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;| **Width** *ID*\
&nbsp;&nbsp;&nbsp;&nbsp;|  *ИД* маски\
&nbsp;&nbsp;&nbsp;&nbsp;| **size** *сизеарг*\
&nbsp;&nbsp;&nbsp;&nbsp;| **sizeof** *сизеарг*\
&nbsp;&nbsp;&nbsp;&nbsp;| **length** *ID*\
&nbsp;&nbsp;&nbsp;&nbsp;| **LENGTHOF** *ID*\
&nbsp;&nbsp;&nbsp;&nbsp;| *рекордконст*\
&nbsp;&nbsp;&nbsp;&nbsp;| *строка*\
&nbsp;&nbsp;&nbsp;&nbsp;| *константа*\
&nbsp;&nbsp;&nbsp;&nbsp;*тип* | 
&nbsp;&nbsp;&nbsp;&nbsp;| *id*\
&nbsp;&nbsp;&nbsp;&nbsp;| **$**\
&nbsp;&nbsp;&nbsp;&nbsp;| *сегментрегистер*\
&nbsp;&nbsp;&nbsp;&nbsp;| *регистр*\
&nbsp;&nbsp;&nbsp;&nbsp;| **ST**\
&nbsp;&nbsp;&nbsp;&nbsp;| **St** ( *expr* )

*ечодир*\
&nbsp;&nbsp;&nbsp;&nbsp;**ECHO**\
&nbsp;&nbsp;&nbsp;&nbsp;*арбитраритекст* ;; \
% *арбитраритекст* ;; \

*елсеифблокк*\
&nbsp;&nbsp;&nbsp;&nbsp;*елсеифстатемент* ;; \
&nbsp;&nbsp;&nbsp;&nbsp;*директивелист*\
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *елсеифблокк* ⟧ \

*елсеифстатемент*\
&nbsp;&nbsp;&nbsp;&nbsp;**ELSEIF** *constExpr*\
&nbsp;&nbsp;&nbsp;&nbsp;| " **ElseIf** " *constExpr*\
&nbsp;&nbsp;&nbsp;&nbsp;| **елсеифб** *текститем*\
&nbsp;&nbsp;&nbsp;&nbsp;| **елсеифнб** *текститем*\
&nbsp;&nbsp;&nbsp;&nbsp;| **елсеифдеф** *ID*\
&nbsp;&nbsp;&nbsp;&nbsp;| **елсеифндеф** *ID*\
&nbsp;&nbsp;&nbsp;&nbsp;| **елсеифдиф** *текститем* , *текститем*\
&nbsp;&nbsp;&nbsp;&nbsp;| **елсеифдифи** *текститем* , *текститем*\
&nbsp;&nbsp;&nbsp;&nbsp;| **елсеифидн** *текститем* , *текститем*\
&nbsp;&nbsp;&nbsp;&nbsp;| **елсеифидни** *текститем* , *текститем*\
&nbsp;&nbsp;&nbsp;&nbsp;| **ELSEIF1**\
&nbsp;&nbsp;&nbsp;&nbsp;| **ELSEIF2**

*енддир*\
&nbsp;&nbsp;&nbsp;&nbsp;**End** ⟦ *иммекспр* ⟧;;

*ендпдир*\
&nbsp;&nbsp;&nbsp;&nbsp;*procId* **ЕНДП** ;;

*ендсдир*\
&nbsp;&nbsp;&nbsp;&nbsp;*идентификатор* **заканчивается** ;;

*екудир*\
&nbsp;&nbsp;&nbsp;&nbsp;*текстмакроид* **равно** *екутипе* ;;

*екутипе*\
&nbsp;&nbsp;&nbsp;&nbsp;*иммекспр* | *текстлитерал*

*еррордир*\
&nbsp;&nbsp;&nbsp;&nbsp;*ерроропт* ;;

*ерроропт*\
&nbsp;&nbsp;&nbsp;&nbsp; **. ERR** ⟦ *текститем* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;|  **. ЕРРЕ** *constExpr* ⟦ *опттекст* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;|  **. ЕРРНЗ** *constExpr* ⟦ *опттекст* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;|  **. ЕРРБ** *текститем* ⟦ *опттекст* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;|  **. ЕРРНБ** *текститем* ⟦ *опттекст* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;|  **. ЕРРДЕФ** *ID* ⟦ *опттекст* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;|  **. ЕРРНДЕФ** *ID* ⟦ *опттекст* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;|  **. ЕРРДИФ** *текститем* , *текститем* ⟦ *опттекст* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;|  **. ЕРРДИФИ** *текститем* , *текститем* ⟦ *опттекст* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;|  **. ЕРРИДН** *текститем* , *текститем* ⟦ *опттекст* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;|  **. ЕРРИДНИ** *текститем* , *текститем* ⟦ *опттекст* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;|  **. ERR1** ⟦ *текститем* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;|  **. ERR2** ⟦ *текститем* ⟧

*екситдир*\
&nbsp;&nbsp;&nbsp;&nbsp; **. EXIT** &nbsp;&nbsp;&nbsp;&nbsp;⟦ *expr* ⟧;;

*екситмдир*\
&nbsp;&nbsp;&nbsp;&nbsp;: ЕКСИТМ | ЕКСИТМ *текститем*

\ *экспоненты*
&nbsp;&nbsp;&nbsp;&nbsp;E ⟦ *Sign* ⟧ *декнумбер*

*выражение*\
&nbsp;&nbsp;&nbsp;&nbsp;**Short** *E05*\
&nbsp;&nbsp;&nbsp;&nbsp;|  **. Введите** E01 \
&nbsp;&nbsp;&nbsp;&nbsp;| **OPATTR** *E01*\
&nbsp;&nbsp;&nbsp;&nbsp;| *E01*

*експрлист*\
&nbsp;&nbsp;&nbsp;&nbsp;*expr* | *експрлист* , *expr*

*екстерндеф*\
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *лангтипе* ⟧ *ID* ⟦ ( *АЛТИД* ) ⟧: *екстернтипе*

*екстерндир*\
&nbsp;&nbsp;&nbsp;&nbsp;*екстернкэй* *екстернлист* ;;

*екстернкэй*\
&nbsp;&nbsp;&nbsp;&nbsp;**екстрн** | **extern** | **екстерндеф**

*екстернлист*\
&nbsp;&nbsp;&nbsp;&nbsp;*екстерндеф* | *екстернлист* , ⟦;; ⟧ *екстерндеф*

*екстернтипе*\
&nbsp;&nbsp;&nbsp;&nbsp;**ABS** | *куалифиедтипе*

*фиелдалигн*\
&nbsp;&nbsp;&nbsp;&nbsp;*constExpr*

*фиелдинит*\
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *инитвалуе* ⟧ | *структинстанце*

*фиелдинитлист*\
&nbsp;&nbsp;&nbsp;&nbsp;*фиелдинит* | *фиелдинитлист* , ⟦;; ⟧ *фиелдинит*

*филечар*\
&nbsp;&nbsp;&nbsp;&nbsp;*разделителем*

*филечарлист*\
&nbsp;&nbsp;&nbsp;&nbsp;*филечар* | *филечарлист* *филечар*

*fileSpec*\
&nbsp;&nbsp;&nbsp;&nbsp;*филечарлист* | *текстлитерал*

*flagName*\
&nbsp;&nbsp;&nbsp;&nbsp;**нуля?** | **выполнить?****переполнение  | ?** | **подписаться?** |  **?**

*флоатнумбер*\
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *Sign* ⟧ *декнумбер* . ⟦ *декнумбер* ⟧ ⟦ *экспонента* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;| *цифры* R | *цифры* r

*форкдир*\
&nbsp;&nbsp;&nbsp;&nbsp;**форк** | **ирпк**

*фордир*\
&nbsp;&nbsp;&nbsp;&nbsp;**для** | **IRP**

*форпарм*\
&nbsp;&nbsp;&nbsp;&nbsp;*ID* ⟦: *форпармтипе* ⟧

*форпармтипе*\
&nbsp;&nbsp;&nbsp;&nbsp;**req** | = *текстлитерал*

*фпурегистер*\
&nbsp;&nbsp; **&nbsp;&nbsp;** *expr*

*фрамикспр*\
&nbsp;&nbsp;&nbsp;&nbsp;**SEG** *ID*\
&nbsp;&nbsp;&nbsp;&nbsp;| **дграуп** : *ID*\
&nbsp;&nbsp;&nbsp;&nbsp;| *сегментрегистер* : *ID*\
&nbsp;&nbsp;&nbsp;&nbsp;*идентификатор* | 

*женералдир*\
&nbsp;&nbsp;&nbsp;&nbsp;*моделдир* | *сегордердир* | *намедир*\
&nbsp;&nbsp;&nbsp;&nbsp;| *инклуделибдир* | *комментдир*\
&nbsp;&nbsp;&nbsp;&nbsp;| *граупдир* | *ассумедир*\
&nbsp;&nbsp;&nbsp;&nbsp;| *структдир* | *рекорддир* | *типедефдир*\
&nbsp;&nbsp;&nbsp;&nbsp;| *екстерндир* | *публикдир* | *коммдир* | *прототипедир*\
&nbsp;&nbsp;&nbsp;&nbsp;| *екудир* | = Dir | *текстдир*\
&nbsp;&nbsp;&nbsp;&nbsp;| *контекстдир* | *оптиондир* | *процессордир*\
&nbsp;&nbsp;&nbsp;&nbsp;| *радиксдир*\
&nbsp;&nbsp;&nbsp;&nbsp;| *титледир* | *пажедир* | *листдир*\
&nbsp;&nbsp;&nbsp;&nbsp;| *крефдир* | *ечодир*\
&nbsp;&nbsp;&nbsp;&nbsp;| *ифдир* | *еррордир* | *инклудедир*\
&nbsp;&nbsp;&nbsp;&nbsp;| *макродир* | *макрокалл* | *макрорепеат* | *пуржедир*\
&nbsp;&nbsp;&nbsp;&nbsp;| *макровхиле* | *макрофор* | *макрофорк*\
&nbsp;&nbsp;&nbsp;&nbsp;| *алиасдир*

*гпрегистер*\
&nbsp;&nbsp;&nbsp;&nbsp;AX | EAX | CX | ECX | DX | EDX | BX | EBX | DI | EDI | SI | ESI | BP | EBP | SP | ESP | RSP | R8W | R8D | R9W | R9D | R12D | R13W | R13D | R14W | R14D

*граупдир*\
&nbsp;&nbsp; *&nbsp;&nbsp;* **группы** *сегидлист*

*groupId*\
&nbsp;&nbsp;&nbsp;&nbsp;*ID*

*хексдигит*\
&nbsp;&nbsp;&nbsp;&nbsp;a | б | c | г | e | f | A | Б | C | Г | E | Ж

*идентификатор*\
&nbsp;&nbsp;&nbsp;&nbsp;первым символом идентификатора может быть алфавитный знак верхнего или нижнего регистра (`[A–Za-z]`) или любой из этих четырех символов: `@ _ $ ?` остальные символы могут быть любого из этих же символов или десятичной цифры (`[0–9]`). Максимальная длина — 247 символов.

*idList*\
&nbsp;&nbsp;&nbsp;&nbsp;*id* | *idList* , *ID*

*ифдир*\
&nbsp;&nbsp;&nbsp;&nbsp;*ифстатемент* ;; \
&nbsp;&nbsp;&nbsp;&nbsp;*директивелист*\
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *елсеифблокк* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;⟦ **else** ;; \
&nbsp;&nbsp;&nbsp;&nbsp;*директивелист* ⟧;; \

*ифстатемент*\
&nbsp;&nbsp;&nbsp;&nbsp;, **Если** *constExpr*\
&nbsp;&nbsp;&nbsp;&nbsp;| **Ифе** *constExpr*\
&nbsp;&nbsp;&nbsp;&nbsp;| **ИФБ** *текститем*\
&nbsp;&nbsp;&nbsp;&nbsp;| **ифнб** *текститем*\
&nbsp;&nbsp;&nbsp;&nbsp;| **IFDEF** *ID*\
&nbsp;&nbsp;&nbsp;&nbsp;| **IFNDEF** *ID*\
&nbsp;&nbsp;&nbsp;&nbsp;| **ифдиф** *текститем* , *текститем*\
&nbsp;&nbsp;&nbsp;&nbsp;| **ифдифи** *текститем* , *текститем*\
&nbsp;&nbsp;&nbsp;&nbsp;| **ифидн** *текститем* , *текститем*\
&nbsp;&nbsp;&nbsp;&nbsp;| **ифидни** *текститем* , *текститем*\
&nbsp;&nbsp;&nbsp;&nbsp;| **IF1**\
&nbsp;&nbsp;&nbsp;&nbsp;| **If2**

*иммекспр*\
&nbsp;&nbsp;&nbsp;&nbsp;*expr*

*инклудедир*\
&nbsp;&nbsp;&nbsp;&nbsp; **:** *filespec* ;;

*инклуделибдир*\
&nbsp;&nbsp;&nbsp;&nbsp;**инклуделиб** *;;*

*инитвалуе*\
&nbsp;&nbsp;&nbsp;&nbsp;*иммекспр*\
&nbsp;&nbsp;&nbsp;&nbsp;| *строка*\
&nbsp;&nbsp;&nbsp;&nbsp;|? \
&nbsp;&nbsp;&nbsp;&nbsp;| *constExpr* **DUP** ( *скаларинстлист* ) \
&nbsp;&nbsp;&nbsp;&nbsp;| *флоатнумбер*\
&nbsp;&nbsp;&nbsp;&nbsp;| *бкдконст*

*инсегдир*\
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *лабелдеф* ⟧ *инсегментдир*

*инсегдирлист*\
&nbsp;&nbsp;&nbsp;&nbsp;*инсегдир* | *инсегдирлист* *инсегдир*

*инсегментдир*\
&nbsp;&nbsp;&nbsp;*инструкции* &nbsp;\
&nbsp;&nbsp;&nbsp;&nbsp;| *dataDir*\
&nbsp;&nbsp;&nbsp;&nbsp;| *контролдир*\
&nbsp;&nbsp;&nbsp;&nbsp;| *стартупдир*\
&nbsp;&nbsp;&nbsp;&nbsp;| *екситдир*\
&nbsp;&nbsp;&nbsp;&nbsp;| *оффсетдир*\
&nbsp;&nbsp;&nbsp;&nbsp;| *лабелдир*\
&nbsp;&nbsp;&nbsp;&nbsp;| *прокдир* ⟦ *Локалдирлист* ⟧ ⟦ *инсегдирлист* ⟧ *ендпдир*\
&nbsp;&nbsp;&nbsp;&nbsp;| *инвокедир*\
&nbsp;&nbsp;&nbsp;&nbsp;| *женералдир*

*инстрпрефикс*\
&nbsp;&nbsp;&nbsp;&nbsp;**представитель** | **репе** | **репз** | **Репне** | **репнз** | **Lock**

\ *инструкции*
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *инстрпрефикс* ⟧ *асминструктион*

*инвокеарг*\
&nbsp;&nbsp;&nbsp;&nbsp;*Register* :: *register* | *expr* | **addr** *expr*

*инвокедир*\
&nbsp;&nbsp;&nbsp;&nbsp;**Invoke** *expr* ⟦, ⟦;; ⟧ *инвокелист* ⟧;;

*инвокелист*\
&nbsp;&nbsp;&nbsp;&nbsp;*инвокеарг* | *инвокелист* , ⟦;; ⟧ *инвокеарг*

*ключевое слово*\
&nbsp;&nbsp;&nbsp;&nbsp;любого зарезервированного слова.

*кэйвордлист*\
&nbsp;&nbsp;&nbsp;&nbsp;*ключевое слово* | *ключевое слово* *кэйвордлист*

*лабелдеф*\
&nbsp;&nbsp;&nbsp;&nbsp;*ID* : | *идентификатор* :: | @@:

*лабелдир*\
&nbsp;&nbsp;&nbsp;&nbsp; **метки** идентификатора *куалифиедтипе* ;;

*лангтипе*\
&nbsp;&nbsp;&nbsp;&nbsp;**C** | **PASCAL** | **FORTRAN** | **Basic** | **syscall** | **STDCALL**

*листдир*\
&nbsp;&nbsp;&nbsp;&nbsp;*листоптион* ;;

*листоптион*\
&nbsp;&nbsp;&nbsp;&nbsp; **.\ списка**
&nbsp;&nbsp;&nbsp;&nbsp;|  **.** \ со списком
&nbsp;&nbsp;&nbsp;&nbsp;|  **. КСЛИСТ**\
&nbsp;&nbsp;&nbsp;&nbsp;|  **. ЛИСТАЛЛ**\
&nbsp;&nbsp;&nbsp;&nbsp;|  **. ЛИСТИФ**\
&nbsp;&nbsp;&nbsp;&nbsp;|  **. ЛФКОНД**\
&nbsp;&nbsp;&nbsp;&nbsp;|  **. НОЛИСТИФ**\
&nbsp;&nbsp;&nbsp;&nbsp;|  **. СФКОНД**\
&nbsp;&nbsp;&nbsp;&nbsp;|  **. ТФКОНД**\
&nbsp;&nbsp;&nbsp;&nbsp;|  **.**  | листмакроалл **. ЛАЛЛ**\
&nbsp;&nbsp;&nbsp;&nbsp;|  **.**  | нолистмакро **. Салл**\
&nbsp;&nbsp;&nbsp;&nbsp;|  **.**  | листмакро **. КСАЛЛ**\

*локалдеф*\
&nbsp;&nbsp;&nbsp;&nbsp;**Local** *idList* ;;

*локалдир*\
&nbsp;&nbsp;&nbsp;&nbsp;**Local** *пармлист* ;;

*локалдирлист*\
&nbsp;&nbsp;&nbsp;&nbsp;*локалдир* | *локалдирлист* *локалдир*

*локаллист*\
&nbsp;&nbsp;&nbsp;&nbsp;*локалдеф* | *локаллист* *локалдеф*

*макроарг*\
 % *constExpr*\
&nbsp;&nbsp;&nbsp;&nbsp;| %*текстмакроид*\
&nbsp;&nbsp;&nbsp;&nbsp;| %*макрофунЦид* ( *макроарглист* ) \
&nbsp;&nbsp;&nbsp;&nbsp;| *строка*\
&nbsp;&nbsp;&nbsp;&nbsp;| *арбитраритекст*\
&nbsp;&nbsp;&nbsp;&nbsp;| < *арбитраритекст* >

*макроарглист*\
&nbsp;&nbsp;&nbsp;&nbsp;*макроарг* | *макроарглист* , *макроарг*

*макрободи*\
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *локаллист* ⟧ *макростмтлист*

*макрокалл*\
&nbsp;&nbsp;&nbsp;&nbsp;*ID* *макроарглист* ;; \
&nbsp;&nbsp;&nbsp;&nbsp;| *ID* ( *макроарглист* )

*макродир*\
&nbsp;&nbsp;&nbsp;&nbsp;*ID* **макрос** ⟦ *макропармлист* ⟧;; \
&nbsp;&nbsp;&nbsp;&nbsp;*макрободи*\
&nbsp;&nbsp;&nbsp;&nbsp;**ендм** ;;

*макрофор*\
&nbsp;&nbsp;&nbsp;&nbsp;*фордир* *Форпарм* , < *макроарглист* >;; \
&nbsp;&nbsp;&nbsp;&nbsp;*макрободи*\
&nbsp;&nbsp;&nbsp;&nbsp;**ендм** ;;

*макрофорк*\
&nbsp;&nbsp;&nbsp;&nbsp;*форкдир* *ID* , *текстлитерал* ;; \
&nbsp;&nbsp;&nbsp;&nbsp;*макрободи*\
&nbsp;&nbsp;&nbsp;&nbsp;**ендм** ;;

*макрофунЦид*\
&nbsp;&nbsp;&nbsp;&nbsp;*ID*

*макроид*\
&nbsp;&nbsp;&nbsp;&nbsp;*макропроЦид* | *макрофунЦид*

*макроидлист*\
&nbsp;&nbsp;&nbsp;&nbsp;*макроид* | *макроидлист* , *макроид*

*макролабел*\
&nbsp;&nbsp;&nbsp;&nbsp;*ID*

*макропарм*\
&nbsp;&nbsp;&nbsp;&nbsp;*ID* ⟦: *пармтипе* ⟧

*макропармлист*\
&nbsp;&nbsp;&nbsp;&nbsp;*макропарм* | *макропармлист* , ⟦;; ⟧ *макропарм*

*макропроЦид*\
&nbsp;&nbsp;&nbsp;&nbsp;*ID*

*макрорепеат*\
&nbsp;&nbsp;&nbsp;&nbsp;*репеатдир* *constExpr* ;; \
&nbsp;&nbsp;&nbsp;&nbsp;*макрободи*\
&nbsp;&nbsp;&nbsp;&nbsp;**ендм** ;;

*макростмт*\
&nbsp;&nbsp;&nbsp;*директива* &nbsp; \
&nbsp;&nbsp;&nbsp;&nbsp;| *екситмдир*\
&nbsp;&nbsp;&nbsp;&nbsp;| : *макролабел*\
&nbsp;&nbsp;&nbsp;&nbsp;| **GOTO**\
&nbsp;&nbsp;&nbsp;&nbsp;*макролабел*

*макростмтлист*\
&nbsp;&nbsp;&nbsp;&nbsp;*макростмт* ;; \
&nbsp;&nbsp;&nbsp;&nbsp;| *макростмтлист* *макростмт* ;; \

*макровхиле*\
&nbsp;&nbsp;&nbsp;&nbsp;**while** *constExpr* ;; \
&nbsp;&nbsp;&nbsp;&nbsp;*макрободи*\
&nbsp;&nbsp;&nbsp;&nbsp;**ендм** ;;

*маптипе*\
&nbsp;&nbsp;&nbsp;&nbsp;**все** | **нет** | **нотпублик**

*мемоптион*\
&nbsp;&nbsp;&nbsp;&nbsp;**крошечные** | **небольшие** | **средние** | **Compact** | **большие** | **огромные** ** | **

*назначенная*\
&nbsp;&nbsp;&nbsp;имя инструкции &nbsp;.

*моделдир*\
&nbsp;&nbsp;&nbsp;&nbsp; **.\ модели**
&nbsp;&nbsp;&nbsp;&nbsp;*мемоптион* ⟦, *моделоптлист* ⟧;;

*моделопт*\
&nbsp;&nbsp;&nbsp;&nbsp;*лангтипе* | *стаккоптион*

*моделоптлист*\
&nbsp;&nbsp;&nbsp;&nbsp;*моделопт* | *моделоптлист* , *моделопт*

\ *модуля*
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *директивелист* ⟧ *енддир*

*мулоп*\
&nbsp;&nbsp;&nbsp;&nbsp;\* | / | **Mod**

*намедир*\
&nbsp;&nbsp;&nbsp;&nbsp;**имя**\
&nbsp;&nbsp;&nbsp;&nbsp;*ID* ;; \

*неарфар*\
&nbsp;&nbsp;&nbsp;&nbsp;**около** | 

*нестедструкт*\
&nbsp;&nbsp;&nbsp;&nbsp;*струксдр* ⟦ *ID* ⟧;; \
&nbsp;&nbsp;&nbsp;&nbsp;*структбоди*\
&nbsp;&nbsp;&nbsp;&nbsp;**заканчивается** ;; \

*оффсетдир*\
&nbsp;&nbsp;&nbsp;&nbsp;*оффсетдиртипе* ;;

*оффсетдиртипе*\
&nbsp;&nbsp;&nbsp;&nbsp;**даже** | **org** *иммекспр* | **Выравнивание** ⟦ *constExpr* ⟧

*оффсеттипе*\
&nbsp;&nbsp;&nbsp;&nbsp;**группу** | **сегмент** | **Flat**

*олдрекордфиелдлист*\
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *constExpr* ⟧ | *олдрекордфиелдлист* , ⟦ *constExpr* ⟧

*оптиондир*\
&nbsp;&nbsp;&nbsp;&nbsp;**параметр** *оптионлист* ;;

*оптионитем*\
&nbsp;&nbsp;&nbsp;&nbsp;**касемап** : *маптипе*\
&nbsp;&nbsp;&nbsp;&nbsp;| **дотнаме** | **нодотнаме**\
&nbsp;&nbsp;&nbsp;&nbsp;| **эмулятор** | Emulator **\**
&nbsp;&nbsp;&nbsp;&nbsp;| **эпилога** : *макроид*\
&nbsp;&nbsp;&nbsp;&nbsp;| **EXPR16** | **EXPR32**\
&nbsp;&nbsp;&nbsp;&nbsp;| **Language** : *лангтипе*\
&nbsp;&nbsp;&nbsp;&nbsp;| **лжмп**
| **нолжмп**\
&nbsp;&nbsp;&nbsp;&nbsp;| **M510** | **NOM510**\
&nbsp;&nbsp;&nbsp;&nbsp;| **ключевоеслово** : < *кэйвордлист* >\
&nbsp;&nbsp;&nbsp;&nbsp;| **носигнекстенд**\
&nbsp;&nbsp;&nbsp;&nbsp;| **offset** : *оффсеттипе*\
&nbsp;&nbsp;&nbsp;&nbsp;| **олдмакрос** | **нулдмакрос**\
&nbsp;&nbsp;&nbsp;&nbsp;| **олдструктс** | **нулдструктс**\
&nbsp;&nbsp;&nbsp;&nbsp;| **proc** : *овисибилити*\
&nbsp;&nbsp;&nbsp;&nbsp;| **пролога** : *макроид*\
&nbsp;&nbsp;&nbsp;&nbsp;| **только для** **чтения | \**
&nbsp;&nbsp;&nbsp; **&nbsp;| с заданной областью** ** | **
&nbsp;&nbsp;&nbsp;&nbsp;| **сегмент** : *сегсизе*\
&nbsp;&nbsp;&nbsp;&nbsp;| **SETIF2** : bool

*оптионлист*\
&nbsp;&nbsp;&nbsp;&nbsp;*оптионитем* | *оптионлист* , ⟦;; ⟧ *оптионитем*

*опттекст*\
&nbsp;&nbsp;&nbsp;&nbsp;, *текститем*

*ороп*\
&nbsp;&nbsp;&nbsp;&nbsp;**или** | **XOR**

*овисибилити*\
&nbsp;&nbsp;&nbsp;&nbsp;**PUBLIC** | **частный** | **Экспорт**

*пажедир*\
&nbsp;&nbsp;&nbsp;&nbsp;**Page** ⟦ *пажеекспр* ⟧;;

*пажеекспр*\
&nbsp;&nbsp;&nbsp;&nbsp;\+ | ⟦ *пажеленгс* ⟧ ⟦, *PageWidth* ⟧

*пажеленгс*\
&nbsp;&nbsp;&nbsp;&nbsp;*constExpr*

*pageWidth*\
&nbsp;&nbsp;&nbsp;&nbsp;*constExpr*

*parm*\
&nbsp;&nbsp;&nbsp;&nbsp;*пармид* ⟦: *куалифиедтипе* ⟧ | *пармид* ⟦ *constExpr* ⟧ ⟦: *куалифиедтипе* ⟧

*пармид*\
&nbsp;&nbsp;&nbsp;&nbsp;*ID*

*пармлист*\
&nbsp;&nbsp;&nbsp;&nbsp;*parm* | *пармлист* , ⟦;; ⟧ *ParM*

*пармтипе*\
&nbsp;&nbsp;&nbsp;&nbsp;**req** | = *текстлитерал* | **VARARG**

*поптионс*\
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *Distance* ⟧ ⟦ *Лангтипе* ⟧ ⟦ *овисибилити* ⟧

*первичный*\
&nbsp;&nbsp;&nbsp;&nbsp;*expr* *Бинарйоп* *expr* | *flagName* | *expr*

*прокдир*\
&nbsp;&nbsp;&nbsp;&nbsp;*procId* **proc**\
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *поптионс* ⟧ ⟦ < *макроарглист* > ⟧
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *усесрегс* ⟧ ⟦ *прокпармлист* ⟧

\ *процессора*
&nbsp;&nbsp;&nbsp;&nbsp;|. 386 |. 386P |. 486 |. 486P \
&nbsp;&nbsp;&nbsp;&nbsp;|. 586 |. 586P |. 686 |. 686P |. 387

*процессордир*\
&nbsp;&nbsp;&nbsp;&nbsp;*процессор* ;; \
&nbsp;&nbsp;&nbsp;&nbsp;| *сопроцессора* ;;

*procId*\
&nbsp;&nbsp;&nbsp;&nbsp;*ID*

*проЦитем*\
&nbsp;&nbsp;&nbsp;&nbsp;*инстрпрефикс* | *dataDir* | *лабелдир* | *оффсетдир* | *женералдир*

*прокпармлист*\
&nbsp;&nbsp;&nbsp;&nbsp;⟦, ⟦;; ⟧ *пармлист* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;⟦, ⟦;; ⟧ *пармид* : VARARG ⟧

*протоарг*\
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *ID* ⟧: *куалифиедтипе*

*протоарглист*\
&nbsp;&nbsp;&nbsp;&nbsp;⟦, ⟦;; ⟧ *протолист* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;⟦, ⟦;; ⟧ ⟦ *ID* ⟧: VARARG ⟧

*протолист*\
&nbsp;&nbsp;&nbsp;&nbsp;*протоарг*\
&nbsp;&nbsp;&nbsp;&nbsp;| *протолист* , ⟦;; ⟧ *протоарг*

*протоспек*\
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *Distance* ⟧ ⟦ *Лангтипе* ⟧ ⟦ *протоарглист* ⟧ | *идентификатор* типа

*прототипедир*\
&nbsp;&nbsp;&nbsp;&nbsp;*ID* *протоспек*

*пубдеф*\
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *лангтипе* ⟧ *ID*

*публикдир*\
&nbsp;&nbsp;&nbsp;&nbsp;**Public** *публист* ;;

*публист*\
&nbsp;&nbsp;&nbsp;&nbsp;*пубдеф* | *публист* , ⟦;; ⟧ *пубдеф*

*пуржедир*\
&nbsp;&nbsp;&nbsp;&nbsp;**очистки** *макроидлист*

*куалифиедтипе*\
&nbsp;&nbsp;&nbsp;*тип* &nbsp;| ⟦ *Distance* ⟧ **ptr** ⟦ *куалифиедтипе* ⟧

*квалификатор*\
&nbsp;&nbsp;&nbsp;&nbsp;*куалифиедтипе* |  *протоспек*

*цитата*\
&nbsp;&nbsp;&nbsp;&nbsp;"|"

*квордрегистер*\
&nbsp;&nbsp;&nbsp;&nbsp;RAX | РККС | RDX | РБКС | RDI | РСИ | РБП | R8 | R9 | R10 | R11 | R12 | R13 | R14 | R15

*радиксдир*\
&nbsp;&nbsp;&nbsp;&nbsp; **.**  *CONSTEXPR* системы счисления;;

*радиксоверриде*\
&nbsp;&nbsp;&nbsp;&nbsp;h | o | вопросы | t | y | H | O | Вопросы | T | &

*рекордконст*\
&nbsp;&nbsp;&nbsp;&nbsp;*рекордтаг* { *олдрекордфиелдлист* } | *рекордтаг* < *олдрекордфиелдлист* >

*рекорддир*\
&nbsp;&nbsp;&nbsp;&nbsp; **запись** рекордтаг *битдефлист* ;;

*рекордфиелдлист*\
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *constExpr* ⟧ | *рекордфиелдлист* , ⟦;; ⟧ ⟦ *constExpr* ⟧

*рекординстанце*\
 {⟦;; ⟧ *рекордфиелдлист* ⟦;; ⟧} \
&nbsp;&nbsp;&nbsp;&nbsp;| < *олдрекордфиелдлист* >\
&nbsp;&nbsp;&nbsp;&nbsp;| *constExpr* **DUP** ( *рекординстанце* )

*рекординстлист*\
&nbsp;&nbsp;&nbsp;&nbsp;*рекординстанце* | *рекординстлист* , ⟦;; ⟧ *рекординстанце*

*рекордтаг*\
&nbsp;&nbsp;&nbsp;&nbsp;*ID*

*регистрация*\
&nbsp;&nbsp;&nbsp;&nbsp;*спеЦиалрегистер* | *гпрегистер* | *битерегистер* | *квордрегистер* |  *фпурегистер* | *симдрегистер* | *сегментрегистер*

*реглист*\
&nbsp;&nbsp;&nbsp;&nbsp;*register* |  *регистр* реглист

*relOp*\
&nbsp;&nbsp;&nbsp;&nbsp;EQ | NE | LT | LE | GT | GE

*репеатблокк*\
&nbsp;&nbsp;&nbsp;&nbsp; **. ПОВТОРИТЬ** ;; \
&nbsp;&nbsp;&nbsp;&nbsp;*блоккстатементс* ;; Унтилдир;;

*репеатдир*\
&nbsp;&nbsp;&nbsp;&nbsp;**повторить** |  повтор

*скаларинстлист*\
&nbsp;&nbsp;&nbsp;&nbsp;*инитвалуе* | *скаларинстлист* , ⟦;; ⟧ *инитвалуе*

*сегалигн*\
&nbsp;&nbsp;&nbsp;&nbsp;**BYTE** | **WORD** | **DWORD** | **абзац** | **Page**

*сегаттриб*\
&nbsp;&nbsp;&nbsp;&nbsp;**общедоступный** **стек** |  | **Общие** | **памяти** | **в** *constExpr* | **Private**

*сегдир*\
&nbsp;&nbsp;&nbsp;&nbsp; **.\ кода**
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *сегид* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;|  **.\ данных**
&nbsp;&nbsp;&nbsp;&nbsp;|   **. ДАННЫЕ**\
&nbsp;&nbsp;&nbsp;&nbsp;|  **. КОНСТАНТное**\
&nbsp;&nbsp;&nbsp;&nbsp;|  **. ФАРДАТА**⟦ *сегид* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;|   **. ФАРДАТА?** ⟦ *сегид* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;|  **. STACK** ⟦ *constExpr* ⟧

*сегид*\
&nbsp;&nbsp;&nbsp;&nbsp;*ID*

*сегидлист*\
&nbsp;&nbsp;&nbsp;&nbsp;*сегид*\
&nbsp;&nbsp;&nbsp;&nbsp;| *сегидлист* , *сегид*

*сегментдеф*\
&nbsp;&nbsp;&nbsp;&nbsp;*сегментдир* ⟦ *инсегдирлист* ⟧ *ендсдир* | *симплесегдир* ⟦ *инсегдирлист* ⟧ ⟦ *ендсдир* ⟧

*сегментдир*\
&nbsp;&nbsp;&nbsp;&nbsp;*сегид* **сегмент** ⟦ *сегоптионлист* ⟧;;

*сегментрегистер*\
&nbsp;&nbsp;&nbsp;&nbsp;**CS** | **DS** | **ES** | **FS** | **GS** | **SS**

*сегоптион*\
&nbsp;&nbsp;&nbsp;&nbsp;*сегалигн*\
&nbsp;&nbsp;&nbsp;&nbsp;| *сегро*\
&nbsp;&nbsp;&nbsp;&nbsp;| *сегаттриб*\
&nbsp;&nbsp;&nbsp;&nbsp;| *сегсизе*\
&nbsp;&nbsp;&nbsp;&nbsp;| *className*

*сегоптионлист*\
&nbsp;&nbsp;&nbsp;&nbsp;*сегоптион* | *сегоптионлист* *сегоптион*

*сегордердир*\
&nbsp;&nbsp;&nbsp;&nbsp; **. Альфа** - |  **. SEQ** |  **. ДОССЕГ** | **доссег**

*сегро*\
&nbsp;&nbsp;&nbsp;&nbsp;**ReadOnly**

*сегсизе*\
&nbsp;&nbsp;&nbsp;&nbsp;**USE16** | **USE32** | **Flat**

*шифтоп*\
&nbsp;&nbsp;&nbsp;&nbsp;**SHR** | **шл**

*Подписывание*\
 - | +

*симдрегистер*\
&nbsp;&nbsp;&nbsp;&nbsp;MM0 | MM1 | MM2 | MM3 | MM4 | MM5 | MM6 | MM7 | График xmmregister | YMM0 | YMM1 | YMM2 | YMM3 | YMM4 | YMM5 | YMM6 | YMM7 | YMM8 | YMM9 | YMM10 | YMM11 | YMM12 | YMM13 | YMM14 | YMM15

*симпликспр*\
 ( *цекспр* ) | *основной*

*симплесегдир*\
&nbsp;&nbsp;&nbsp;&nbsp;*сегдир* ;;

*сизеарг*\
&nbsp;&nbsp;&nbsp;&nbsp;*ID* | *Type* | *E10*

*спеЦиалчарс*\
 : | . | ⟦ | ⟧ | ( | ) | < | > | { | } \
&nbsp;&nbsp;&nbsp;&nbsp;| + | - | / | * | & | % | !\
&nbsp;&nbsp;&nbsp;&nbsp;| ' | \ | = | ; | , | "\
&nbsp;&nbsp;&nbsp;&nbsp;| *вхитеспацечарактер*\
&nbsp;&nbsp;&nbsp;&nbsp;| *ендофлине*

*спеЦиалрегистер*\
&nbsp;&nbsp;&nbsp;&nbsp;CR0 | CR2 | CR3 | DR0 | DR1 | DR2 | DR3 | DR6 | DR7 | TR3 | TR4 | TR5 | TR6 | TR7

*стаккоптион*\
&nbsp;&nbsp;&nbsp;&nbsp;**неарстакк** | **фарстакк**

*стартупдир*\
&nbsp;&nbsp;&nbsp;&nbsp; **. Запуск** ;;

*стекст*\
&nbsp;&nbsp;&nbsp;&nbsp;*стрингчар* | *стекст* *стрингчар*

*string*\
&nbsp;&nbsp;&nbsp;&nbsp;*Quotes* ⟦ *стекст* ⟧ *quote*

*стрингчар*\
&nbsp;&nbsp; *&nbsp;&nbsp;кавычки* *|* Любой символ, кроме кавычек.

*структбоди*\
&nbsp;&nbsp;&nbsp;&nbsp;*структитем* ;; \
&nbsp;&nbsp;&nbsp;&nbsp;| *структбоди* *структитем* ;;

*структдир*\
&nbsp;&nbsp;&nbsp;&nbsp;*структтаг* *струксдр* ⟦ *фиелдалигн* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;⟦, **неуникальный** ⟧;; \
&nbsp;&nbsp;&nbsp;&nbsp;*структбоди*\
&nbsp;&nbsp;&nbsp;&nbsp;*структтаг*\
&nbsp;&nbsp;&nbsp;&nbsp;**завершается** ;;

*струксдр*\
&nbsp;&nbsp;&nbsp;&nbsp;**струк** | **STRUCT** | **Union**

*структинстанце*\
 < ⟦ *фиелдинитлист* ⟧ > \
&nbsp;&nbsp;&nbsp;&nbsp;| {⟦;; ⟧ ⟦ *фиелдинитлист* ⟧ ⟦;; ⟧} \
&nbsp;&nbsp;&nbsp;&nbsp;| *constExpr* **DUP** ( *структинстлист* ) \

*структинстлист*\
&nbsp;&nbsp;&nbsp;&nbsp;*структинстанце* | *структинстлист* , ⟦;; ⟧ *структинстанце*

*структитем*\
&nbsp;&nbsp;&nbsp;&nbsp;*dataDir*\
&nbsp;&nbsp;&nbsp;&nbsp;| *женералдир*\
&nbsp;&nbsp;&nbsp;&nbsp;| *оффсетдир*\
&nbsp;&nbsp;&nbsp;&nbsp;| *нестедструкт*

*структтаг*\
&nbsp;&nbsp;&nbsp;&nbsp;*ID*

\ *термина*
&nbsp;&nbsp;&nbsp;&nbsp;*симпликспр* |! *симпликспр*

*text*\
&nbsp;&nbsp;&nbsp;&nbsp;*текстлитерал* | *текстовый* символ |! *символьный* *текст* | *символ* |! *символ*

*текстдир*\
&nbsp;&nbsp;&nbsp;&nbsp;*ID* *текстмакродир* ;;

*текститем*\
&nbsp;&nbsp;&nbsp;&nbsp;*текстлитерал* | *текстмакроид* | % *constExpr*

*текстлен*\
&nbsp;&nbsp;&nbsp;&nbsp;*constExpr*

*текстлист*\
&nbsp;&nbsp;&nbsp;&nbsp;*текститем* | *текстлист* , ⟦;; ⟧ *текститем*

*текстлитерал*\
&nbsp;&nbsp;&nbsp;&nbsp;< *text* >;;

*текстмакродир*\
&nbsp;&nbsp;&nbsp;&nbsp;**катстр** ⟦ *текстлист* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;| **текстеку** ⟦ *текстлист* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;| **сизестр** *текститем*\
&nbsp;&nbsp;&nbsp;&nbsp;| **substr** *текститем* , *текстстарт* ⟦, *текстлен* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;| **InStr** ⟦ *Текстстарт* , ⟧ *текститем* , *текститем*

*текстмакроид*\
&nbsp;&nbsp;&nbsp;&nbsp;*ID*

*текстстарт*\
&nbsp;&nbsp;&nbsp;&nbsp;*constExpr*

*титледир*\
&nbsp;&nbsp;&nbsp;&nbsp;*титлетипе* *арбитраритекст* ;;

*титлетипе*\
&nbsp;&nbsp;&nbsp;&nbsp;**title** | **подзаголовок** | **субттл**

*type*\
&nbsp;&nbsp;&nbsp;&nbsp;*структтаг*\
&nbsp;&nbsp;&nbsp;&nbsp;| *унионтаг*\
&nbsp;&nbsp;&nbsp;&nbsp;| *рекордтаг*\
&nbsp;&nbsp;&nbsp;&nbsp;| *расстояние*\
&nbsp;&nbsp;&nbsp;&nbsp;| *dataType*\
&nbsp;&nbsp;&nbsp;&nbsp;| *typeId*

*типедефдир*\
Квалификатор &nbsp;&nbsp;&nbsp;&nbsp;*typeId* **TYPEDEF**

\ *typeId*
&nbsp;&nbsp;&nbsp;&nbsp;*ID*

*унионтаг*\
&nbsp;&nbsp;&nbsp;&nbsp;*ID*

*унтилдир*\
&nbsp;&nbsp;&nbsp;&nbsp; **. ДО** *цекспр* ;; \
&nbsp;&nbsp;&nbsp;&nbsp; **. УНТИЛККСЗ** ⟦ *кксзекспр* ⟧;;

*усесрегс*\
&nbsp;&nbsp;&nbsp;&nbsp;**использует** *реглист*

*вхилеблокк*\
&nbsp;&nbsp;&nbsp;&nbsp; **. При**\
&nbsp;&nbsp;&nbsp;&nbsp;*цекспр* ;; \
&nbsp;&nbsp;&nbsp;&nbsp;*блоккстатементс* ;; \
&nbsp;&nbsp;&nbsp;&nbsp; **. ЕНДВ**

*вхитеспацечарактер*\
&nbsp;&nbsp;&nbsp;&nbsp;ASCII 8, 9, 11 – 13, 26, 32

*график xmmregister*\
&nbsp;&nbsp;&nbsp;&nbsp;XMM0 | XMM1 | XMM2 | XMM3 | XMM4 | XMM5 | XMM6 | XMM7 | XMM8 | XMM9 | XMM10 | XMM11 | XMM12 | XMM13 | XMM14 | XMM15\

