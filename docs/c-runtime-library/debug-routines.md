---
title: "Процедуры отладки | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: c.debug
dev_langs: C++
helpviewer_keywords:
- debugging [CRT], using macros
- macros, debugging with
- debug routines
- debug macros
- debugging [CRT], run-time routines
ms.assetid: cb4d2664-10f3-42f7-a516-595558075471
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 158a3b782ffedc7bd206f400c066c052062ad402
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="debug-routines"></a>Процедуры отладки
Отладочная версия библиотеки времени выполнения C предоставляет множество служб диагностики, упрощающих отладку программ и позволяющих разработчикам:  
  
-   пошагово входить непосредственно в функции времени выполнения во время отладки;  
  
-   разрешать утверждения, ошибки и исключения;  
  
-   трассировать выделение памяти в куче и предотвращать утечки памяти;  
  
-   выводить отладочные сообщения пользователю.  
  
 Для использования этих подпрограмм должен быть определен флаг [_DEBUG](../c-runtime-library/debug.md). В окончательной сборке приложения все эти подпрограммы не выполняют никаких действий. Дополнительные сведения о том, как использовать новые подпрограммы отладки, см. в разделе [Методы отладки CRT](/visualstudio/debugger/crt-debugging-techniques).  
  
### <a name="debug-versions-of-the-c-run-time-library-routines"></a>Отладочные версии подпрограмм библиотеки времени выполнения C  
  
|Подпрограмма|Применение|  
|-------------|---------|  
|[_ASSERT](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)|Вычисляет выражение и создает отладочный отчет, когда результат равен FALSE|  
|[_ASSERTE](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)|Аналогична `_ASSERT`, но включает в создаваемый отчет выражение, где произошел сбой|  
|[_CrtCheckMemory](../c-runtime-library/reference/crtcheckmemory.md)|Проверяет целостность выделенных блоков памяти в отладочной куче|  
|[_CrtDbgBreak](../c-runtime-library/reference/crtdbgbreak.md)|Устанавливает точку останова.|  
|[_CrtDbgReport, _CrtDbgReportW](../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md)|Создает отладочный отчет с сообщением для пользователя и отправляет отчет в три возможных назначения|  
|[_CrtDoForAllClientObjects](../c-runtime-library/reference/crtdoforallclientobjects.md)|Вызывает предоставленную приложением функцию для всех типов `_CLIENT_BLOCK` в куче|  
|[_CrtDumpMemoryLeaks](../c-runtime-library/reference/crtdumpmemoryleaks.md)|Сбрасывает все блоки памяти в отладочной куче при значительной утечке памяти|  
|[_CrtIsMemoryBlock](../c-runtime-library/reference/crtismemoryblock.md)|Проверяет, что указанный блок памяти находится в локальной куче, а также что он имеет допустимый идентификатор типа блока отладочной кучи|  
|[_CrtIsValidHeapPointer](../c-runtime-library/reference/crtisvalidheappointer.md)|Проверяет, что указанный указатель находится в локальной куче|  
|[_CrtIsValidPointer](../c-runtime-library/reference/crtisvalidpointer.md)|Проверяет, что указанный диапазон памяти допустим для чтения и записи|  
|[_CrtMemCheckpoint](../c-runtime-library/reference/crtmemcheckpoint.md)|Получает текущее состояние отладочной кучи и сохраняет его в предоставленной приложением структуре `_CrtMemState`|  
|[_CrtMemDifference](../c-runtime-library/reference/crtmemdifference.md)|Сравнивает два состояния памяти на предмет значащих отличий и возвращает результаты|  
|[_CrtMemDumpAllObjectsSince](../c-runtime-library/reference/crtmemdumpallobjectssince.md)|Сбрасывает сведения об объектах в куче с указанной контрольной точки или с начала выполнения программы|  
|[_CrtMemDumpStatistics](../c-runtime-library/reference/crtmemdumpstatistics.md)|Сбрасывает данные заголовка отладки для указанного состояния памяти в понятной пользователю форме|  
|[_CrtReportBlockType](../c-runtime-library/reference/crtreportblocktype.md)|Возвращает тип и подтип блока, связанные с указателем блока заданной отладочной кучи.|  
|[_CrtSetAllocHook](../c-runtime-library/reference/crtsetallochook.md)|Устанавливает определяемую клиентом функцию выделения путем присоединения ее к отладочному процессу выделения памяти времени выполнения C|  
|[_CrtSetBreakAlloc](../c-runtime-library/reference/crtsetbreakalloc.md)|Устанавливает точку останова на указанном порядковом номере выделения объекта|  
|[_CrtSetDbgFlag](../c-runtime-library/reference/crtsetdbgflag.md)|Извлекает или изменяет состояние флага `_crtDbgFlag` для управления поведением выделения диспетчера отладочной кучи|  
|[_CrtSetDumpClient](../c-runtime-library/reference/crtsetdumpclient.md)|Устанавливает определяемую приложением функцию, которая вызывается при каждом вызове функции отладочного дампа для сброса блоков памяти типа `_CLIENT_BLOCK`|  
|[_CrtSetReportFile](../c-runtime-library/reference/crtsetreportfile.md)|Указывает файл или поток, используемый в качестве назначения для определенного типа отчета `_CrtDbgReport`|  
|[_CrtSetReportHook](../c-runtime-library/reference/crtsetreporthook.md)|Устанавливает определяемую клиентом функцию отчетов путем присоединения ее к отладочному процессу отчетов времени выполнения С|  
|[_CrtSetReportHook2, _CrtSetReportHookW2](../c-runtime-library/reference/crtsetreporthook2-crtsetreporthookw2.md)|Устанавливает или удаляет определяемую клиентом функцию отчетов путем ее присоединения к отладочному процессу отчетов времени выполнения языка C.|  
|[_CrtSetReportMode](../c-runtime-library/reference/crtsetreportmode.md)|Задает общие назначения для определенного типа отчета, создаваемого `_CrtDbgReport`|  
|[_RPT&#91;0,1,2,3,4&#93;](../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md)|Отслеживает ход выполнения приложения путем создания отладочного отчета, вызывая `_CrtDbgReport` со строкой формата и переменным количеством аргументов. Не предоставляет сведений об исходном файле и номере строки.|  
|[_RPTF&#91;0,1,2,3,4&#93;](../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md)|Аналогична макросам `_RPTn`, но предоставляет имя файла и номер строки в файле, где возник запрос отчета|  
|[_calloc_dbg](../c-runtime-library/reference/calloc-dbg.md)|Выделяет указанное количество блоков памяти в куче с дополнительным местом для отладочного заголовка и буферов перезаписи|  
|[_expand_dbg](../c-runtime-library/reference/expand-dbg.md)|Изменяет размер указанного блока памяти в куче, увеличивая его или сжимая|  
|[_free_dbg](../c-runtime-library/reference/free-dbg.md)|Освобождает блок памяти в куче|  
|[_fullpath_dbg, _wfullpath_dbg](../c-runtime-library/reference/fullpath-dbg-wfullpath-dbg.md)|Создает абсолютный или полный путь для указанного относительного имени пути, используя [_malloc_dbg](../c-runtime-library/reference/malloc-dbg.md) для выделения памяти.|[System::IO::File::Create](https://msdn.microsoft.com/en-us/library/system.io.file.create.aspx)|  
|[_getcwd_dbg, _wgetcwd_dbg](../c-runtime-library/reference/getcwd-dbg-wgetcwd-dbg.md)|Получает текущий рабочий каталог, используя [_malloc_dbg](../c-runtime-library/reference/malloc-dbg.md) для выделения памяти.|  
|[_malloc_dbg](../c-runtime-library/reference/malloc-dbg.md)|Выделяет блок памяти в куче с дополнительным местом для отладочного заголовка и буферов перезаписи|  
|[_msize_dbg](../c-runtime-library/reference/msize-dbg.md)|Вычисляет размер блока памяти в куче|  
|[_realloc_dbg](../c-runtime-library/reference/realloc-dbg.md)|Перераспределяет указанный блок памяти в куче, перемещая его и (или) изменяя его размер|  
|[_strdup_dbg, _wcsdup_dbg](../c-runtime-library/reference/strdup-dbg-wcsdup-dbg.md)|Создает дубликат строки, используя [_malloc_dbg](../c-runtime-library/reference/malloc-dbg.md) для выделения памяти.|  
|[_tempnam_dbg, _wtempnam_dbg](../c-runtime-library/reference/tempnam-dbg-wtempnam-dbg.md)|Создает имена, которые можно применять для создания временных файлов, используя [_malloc_dbg](../c-runtime-library/reference/malloc-dbg.md) для выделения памяти.|  
  
 Подпрограммы отладки можно использовать для пошагового выполнения исходного кода большинства других подпрограмм времени выполнения C в процессе отладки. Однако Microsoft рассматривает некоторые из технологий как защищаемые законодательством об интеллектуальной собственности и, следовательно, не предоставляет исходный код для этих подпрограмм. Большинство этих подпрограмм относится либо к обработке исключений, либо к группам операций с плавающей запятой, однако есть также несколько подпрограмм других категорий. Эти подпрограммы перечислены в следующей таблице.  
  
### <a name="c-run-time-routines-that-are-not-available-in-source-code-form"></a>Подпрограммы времени выполнения C, недоступные в виде исходного кода  
  
||||  
|-|-|-|  
|[acos, acosf, acosl](../c-runtime-library/reference/acos-acosf-acosl.md)|[_fpclass](../c-runtime-library/reference/fpclass-fpclassf.md)|[_nextafter](../c-runtime-library/reference/nextafter-functions.md)|  
|[asin](../c-runtime-library/reference/asin-asinf-asinl.md)|[_fpieee_flt](../c-runtime-library/reference/fpieee-flt.md)|[pow](../c-runtime-library/reference/pow-powf-powl.md)|  
|[atan, atan2](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)|[_fpreset](../c-runtime-library/reference/fpreset.md)|[printf, _printf_l, wprintf, _wprintf_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md), [printf_s, _printf_s_l, wprintf_s, _wprintf_s_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)*|  
|[_cabs](../c-runtime-library/reference/cabs.md)|[frexp](../c-runtime-library/reference/frexp.md)|[_scalb](../c-runtime-library/reference/scalb.md)|  
|[ceil](../c-runtime-library/reference/ceil-ceilf-ceill.md)|[_hypot](../c-runtime-library/reference/hypot-hypotf-hypotl-hypot-hypotf-hypotl.md)|[scanf, _scanf_l, wscanf, _wscanf_l](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md), [scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l](../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)*|  
|[_chgsign, _chgsignf, _chgsignl](../c-runtime-library/reference/chgsign-chgsignf-chgsignl.md)|[_isnan](../c-runtime-library/reference/isnan-isnan-isnanf.md)|[setjmp](../c-runtime-library/reference/setjmp.md)|  
|[_clear87, _clearfp](../c-runtime-library/reference/clear87-clearfp.md)|[_j0](../c-runtime-library/reference/bessel-functions-j0-j1-jn-y0-y1-yn.md)|[sin](../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)|  
|[_control87, _controlfp, \__control87_2](../c-runtime-library/reference/control87-controlfp-control87-2.md)|[_j1](../c-runtime-library/reference/bessel-functions-j0-j1-jn-y0-y1-yn.md)|[sinh](../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)|  
|[copysign, copysignf, copysignl, _copysign, _copysignf, _copysignl](../c-runtime-library/reference/copysign-copysignf-copysignl-copysign-copysignf-copysignl.md)|[_jn](../c-runtime-library/reference/bessel-functions-j0-j1-jn-y0-y1-yn.md)|[sqrt](../c-runtime-library/reference/sqrt-sqrtf-sqrtl.md)|  
|[cos](../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)|[ldexp](../c-runtime-library/reference/ldexp.md)|[_status87, _statusfp](../c-runtime-library/reference/status87-statusfp-statusfp2.md)|  
|[cosh](../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)|[log](../c-runtime-library/reference/log-logf-log10-log10f.md)|[tan](../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)|  
|[Exp](../c-runtime-library/reference/exp-expf.md)|[log10](../c-runtime-library/reference/log-logf-log10-log10f.md)|[tanh](../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)|  
|[fabs](../c-runtime-library/reference/fabs-fabsf-fabsl.md)|[_logb](../c-runtime-library/reference/logb-logbf-logbl-logb-logbf.md)|[_y0](../c-runtime-library/reference/bessel-functions-j0-j1-jn-y0-y1-yn.md)|  
|[_finite](../c-runtime-library/reference/finite-finitef.md)|[longjmp](../c-runtime-library/reference/longjmp.md)|[_y1](../c-runtime-library/reference/bessel-functions-j0-j1-jn-y0-y1-yn.md)|  
|[floor](../c-runtime-library/reference/floor-floorf-floorl.md)|[_matherr](../c-runtime-library/reference/matherr.md)|[_yn](../c-runtime-library/reference/bessel-functions-j0-j1-jn-y0-y1-yn.md)|  
|[fmod](../c-runtime-library/reference/fmod-fmodf.md)|[modf](../c-runtime-library/reference/modf-modff-modfl.md)||  
  
 \* Хотя для большей части этой подпрограммы исходный код доступен, он осуществляет внутренний вызов другой подпрограммы, для которой исходный код не предоставляется.  
  
 Некоторые функции времени выполнения C и операторы C++ ведут себя иначе при их вызове из отладочной сборки приложения. (Обратите внимание, что отладочную сборку приложения можно выполнить либо путем установки флага `_DEBUG`, либо путем связывания с отладочной версией библиотеки времени выполнения C). Различия в поведении обычно состоят в дополнительных возможностях или в составе сведений, предоставляемых подпрограммой для поддержки процесса отладки. Эти подпрограммы перечислены в следующей таблице.  
  
### <a name="routines-that-behave-differently-in-a-debug-build-of-an-application"></a>Подпрограммы, которые ведут себя иначе в отладочной сборке приложения  
  
|||  
|-|-|  
|Подпрограмма C [abort](../c-runtime-library/reference/abort.md)|Оператор C++ [delete](../cpp/delete-operator-cpp.md)|  
|Подпрограмма C [assert](../c-runtime-library/reference/assert-macro-assert-wassert.md)|Оператор C++ [new](../cpp/new-operator-cpp.md)|  
  
## <a name="see-also"></a>См. также  
 [Процедуры среды выполнения по категориям](../c-runtime-library/run-time-routines-by-category.md)   
 [Проверка ошибок во время выполнения](../c-runtime-library/run-time-error-checking.md)