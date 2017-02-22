---
title: "Процедуры отладки | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.debug"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "отладка [CRT], использование макросов"
  - "макросы, отладка с помощью"
  - "процедуры отладки"
  - "макросы отладки"
  - "отладка [CRT], подпрограммы времени выполнения"
ms.assetid: cb4d2664-10f3-42f7-a516-595558075471
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Процедуры отладки
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Отладочная версия библиотеки времени выполнения C предоставляет множество служб диагностики, упрощающих отладку программы и позволяющих разработчикам:  
  
-   Пошагово входить непосредственно в функции времени выполнения во время отладки  
  
-   Разрешать утверждения, ошибки и исключения  
  
-   Выполнять трассировку выделения памяти и предотвращать утечки памяти  
  
-   Выводить отладочные сообщения пользователю  
  
 Для использования этих процедур должен быть определен флаг [\_DEBUG](../Topic/_DEBUG.md).  Все эти процедуры не выполняют никаких действий в итоговом построении приложения.  Дополнительные сведения о том, как использовать новые отладочные процедуры см. в разделе [CRT Debugging Techniques](../Topic/CRT%20Debugging%20Techniques.md).  
  
### Отладочные версии процедур библиотеки времени выполнения C.  
  
|Подпрограмма|Применение|Эквивалент в .NET Framework|  
|------------------|----------------|---------------------------------|  
|[\_ASSERT](../Topic/_ASSERT,%20_ASSERTE,%20_ASSERT_EXPR%20Macros.md)|Вычисляет выражение и создает отладочный отчет, когда результат FALSE|[\<caps:sentence id\="tgt15" sentenceid\="14fd9bf776829d73028df00162f7533f" class\="tgtSentence"\>System::Diagnostics::Debug::Assert\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.assert.aspx)|  
|[\_ASSERTE](../Topic/_ASSERT,%20_ASSERTE,%20_ASSERT_EXPR%20Macros.md)|Аналогично `_ASSERT`, но не содержит выражение в создаваемом отчете|[\<caps:sentence id\="tgt18" sentenceid\="14fd9bf776829d73028df00162f7533f" class\="tgtSentence"\>System::Diagnostics::Debug::Assert\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.assert.aspx)|  
|[\_CrtCheckMemory](../c-runtime-library/reference/crtcheckmemory.md)|Проверяет целостность выделенных блоков памяти в отладочной куче|[\<caps:sentence id\="tgt20" sentenceid\="e42975224af21ff11a761e6a6bdbd602" class\="tgtSentence"\>System::Diagnostics::PerformanceCounter\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.performancecounter.aspx)|  
|[\_CrtDbgBreak](../Topic/_CrtDbgBreak.md)|Задает точку останова.|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_CrtDbgReport, \_CrtDbgReportW](../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md)|Создает отладочный отчет с сообщением для пользователя и отправляет отчет в три возможные назначения|[System::Diagnostics::Debug::Write](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.write.aspx), [System::Diagnostics::Debug::Writeline](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.writeline.aspx), [System::Diagnostics::Debug::WriteIf](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.writeif.aspx), [System::Diagnostics::Debug::WriteLineIf](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.writelineif.aspx)|  
|[\_CrtDoForAllClientObjects](../c-runtime-library/reference/crtdoforallclientobjects.md)|Вызывает предоставленную приложением функции для всех типов `_CLIENT_BLOCK` в куче|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_CrtDumpMemoryLeaks](../c-runtime-library/reference/crtdumpmemoryleaks.md)|Сбрасывает все блоки памяти в отладочной куче при значительной утечке памяти|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_CrtIsMemoryBlock](../c-runtime-library/reference/crtismemoryblock.md)|Проверяет, что указанный блок памяти находится в локальной куче и что он имеет допустимый идентификатор типа блоков отладочной кучи|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_CrtIsValidHeapPointer](../c-runtime-library/reference/crtisvalidheappointer.md)|Проверяет, что определенный указатель расположен в локальной куче|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_CrtIsValidPointer](../c-runtime-library/reference/crtisvalidpointer.md)|Проверяет, что указанный диапазон памяти допустим для чтения и записи|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_CrtMemCheckpoint](../c-runtime-library/reference/crtmemcheckpoint.md)|Получает текущее состояние отладочной кучи и сохраняет его в предоставленной приложением структуре `_CrtMemState`|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_CrtMemDifference](../Topic/_CrtMemDifference.md)|Сравнивает два состояния памяти на значащие отличия и возвращает результаты|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_CrtMemDumpAllObjectsSince](../Topic/_CrtMemDumpAllObjectsSince.md)|Сбрасывает сведения об объектах в куче после достижения контрольной точки или с самого начала выполнения программы|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_CrtMemDumpStatistics](../Topic/_CrtMemDumpStatistics.md)|Сбрасывает данные заголовка отладки для указанного состояния памяти в понятной пользователю форме|[\<caps:sentence id\="tgt64" sentenceid\="e42975224af21ff11a761e6a6bdbd602" class\="tgtSentence"\>System::Diagnostics::PerformanceCounter\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.performancecounter.aspx)|  
|[\_CrtReportBlockType](../Topic/_CrtReportBlockType.md)|Возвращает тип и подтип блока, связанный с заданным указателем на блок кучи отладки.|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_CrtSetAllocHook](../Topic/_CrtSetAllocHook.md)|Устанавливает определяемую клиентом функцию выделения путём её прикрепления в отладочный процесс выделения памяти среды выполнения языка C.|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_CrtSetBreakAlloc](../c-runtime-library/reference/crtsetbreakalloc.md)|Устанавливает точку останова на указанном порядковом номере выделения объекта|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_CrtSetDbgFlag](../c-runtime-library/reference/crtsetdbgflag.md)|Извлекает или изменяет состояние флага `_crtDbgFlag` для управления поведением выделения диспетчера отладочной кучи|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_CrtSetDumpClient](../c-runtime-library/reference/crtsetdumpclient.md)|Задает определенную приложением функцию, которая вызывается при каждом вызове функции отладочного дампа, чтобы сбросить блоки памяти типа `_CLIENT_BLOCK`|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_CrtSetReportFile](../Topic/_CrtSetReportFile.md)|Указывает файл или поток, используемый в качестве назначения для определенного типа отчета `_CrtDbgReport`|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_CrtSetReportHook](../c-runtime-library/reference/crtsetreporthook.md)|Задает определенную клиентом функцию путем присоединения ее к отладочному процессу уведомлений времени выполнения С.|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_CrtSetReportHook2, \_CrtSetReportHookW2](../c-runtime-library/reference/crtsetreporthook2-crtsetreporthookw2.md)|Устанавливает или отменяет определяемую клиентом функцию отчетов путём её прикрепления в процесс создания отчетов среды выполнения языка C \(только отладочная версия\).|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_CrtSetReportMode](../c-runtime-library/reference/crtsetreportmode.md)|Определяет общие назначения для определенного типа отчета, созданного `_CrtDbgReport`|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_RPT&#91;0,1,2,3,4&#93;](../Topic/_RPT,%20_RPTF,%20_RPTW,%20_RPTFW%20Macros.md)|Отслеживает ход выполнения приложения созданием отладочного отчета путем вызова `_CrtDbgReport` со строкой формата и переменным количеством аргументов.  Не предоставляет информацию о исходном файле и номере строки.|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_RPTF&#91;0,1,2,3,4&#93;](../Topic/_RPT,%20_RPTF,%20_RPTW,%20_RPTFW%20Macros.md)|Аналогична макросам `_RPTn`, но предоставляет имя файла и номер строки в файле, где возник запрос отчета|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_calloc\_dbg](../c-runtime-library/reference/calloc-dbg.md)|Выделяет указанное число блоков памяти в куче с дополнительным местом для отладочного заголовка и буферов перезаписи|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_expand\_dbg](../Topic/_expand_dbg.md)|Изменяет размер указанного блока памяти в куче, увеличивая его или сжимая|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_free\_dbg](../c-runtime-library/reference/free-dbg.md)|Освобождает блок памяти в куче|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_fullpath\_dbg, \_wfullpath\_dbg](../c-runtime-library/reference/fullpath-dbg-wfullpath-dbg.md)|Создает абсолютный или полный путь для указанного относительного имени пути, используя [\_malloc\_dbg](../c-runtime-library/reference/malloc-dbg.md) для выделения памяти.|[\<caps:sentence id\="tgt129" sentenceid\="57f5d14fd2f1847b8e44146f72e48f72" class\="tgtSentence"\>System::IO::File::Create\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.io.file.create.aspx)|  
|[\_getcwd\_dbg, \_wgetcwd\_dbg](../c-runtime-library/reference/getcwd-dbg-wgetcwd-dbg.md)|Получает текущую рабочую папку, используя [\_malloc\_dbg](../c-runtime-library/reference/malloc-dbg.md) выделения памяти.|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_malloc\_dbg](../c-runtime-library/reference/malloc-dbg.md)|Выделяет блок памяти в куче с дополнительным местом для отладочного заголовка и буферов перезаписи|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_msize\_dbg](../c-runtime-library/reference/msize-dbg.md)|Вычисляет размер блока памяти в куче|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_realloc\_dbg](../c-runtime-library/reference/realloc-dbg.md)|Перераспределяет указанный блок памяти в куче, перемещая его и\/или изменяя размер|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_strdup\_dbg, \_wcsdup\_dbg](../Topic/_strdup_dbg,%20_wcsdup_dbg.md)|Дублирует строки, используя [\_malloc\_dbg](../c-runtime-library/reference/malloc-dbg.md) для выделения памяти.|[\<caps:sentence id\="tgt151" sentenceid\="74a4ca1462af4bfed5950888b5c554e1" class\="tgtSentence"\>System::String::Clone\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.string.clone.aspx)|  
|[\_tempnam\_dbg, \_wtempnam\_dbg](../c-runtime-library/reference/tempnam-dbg-wtempnam-dbg.md)|Создает имена, которые можно использовать для создания временных файлов, используя [\_malloc\_dbg](../c-runtime-library/reference/malloc-dbg.md) для выделения памяти.|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
  
 Процедуры отладки можно использовать, чтобы пошагово выполнить исходный код большей части других процедур среды выполнения C в процессе отладки.  Однако Майкрософт считает некоторые технологии собственническими и, следовательно, не предоставляет исходный код для этих процедур.  Большинство этих процедур относится или к обработке исключений, или к группам операций с плавающей запятой, но несколько других также включены.  Эти процедуры перечислены в следующей таблице.  
  
### Подпрограммы среды выполнения C, недоступные в форме исходного кода  
  
||||  
|-|-|-|  
|[acos, acosf, acosl](../c-runtime-library/reference/acos-acosf-acosl.md)|[\_fpclass](../c-runtime-library/reference/fpclass-fpclassf.md)|[\_nextafter](../c-runtime-library/reference/nextafter-functions.md)|  
|[asin](../c-runtime-library/reference/asin-asinf-asinl.md)|[\_fpieee\_flt](../c-runtime-library/reference/fpieee-flt.md)|[pow](../Topic/pow,%20powf,%20powl.md)|  
|[atan, atan2](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)|[\_fpreset](../c-runtime-library/reference/fpreset.md)|[printf, \_printf\_l, wprintf, \_wprintf\_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md), [printf\_s, \_printf\_s\_l, wprintf\_s, \_wprintf\_s\_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)\*|  
|[\_cabs](../Topic/_cabs.md)|[frexp](../c-runtime-library/reference/frexp.md)|[\_scalb](../c-runtime-library/reference/scalb.md)|  
|[ceil](../c-runtime-library/reference/ceil-ceilf-ceill.md)|[\_hypot](../c-runtime-library/reference/hypot-hypotf-hypotl-hypot-hypotf-hypotl.md)|[scanf, \_scanf\_l, wscanf, \_wscanf\_l](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md), [scanf\_s, \_scanf\_s\_l, wscanf\_s, \_wscanf\_s\_l](../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)\*|  
|[\_chgsign, \_chgsignf, \_chgsignl](../c-runtime-library/reference/chgsign-chgsignf-chgsignl.md)|[\_isnan](../c-runtime-library/reference/isnan-isnan-isnanf.md)|[setjmp](../c-runtime-library/reference/setjmp.md)|  
|[\_clear87, \_clearfp](../c-runtime-library/reference/clear87-clearfp.md)|[\_j0](../misc/bessel-functions-j0-j1-jn.md)|[sin](../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)|  
|[\_control87, \_controlfp, \_\_control87\_2](../Topic/_control87,%20_controlfp,%20__control87_2.md)|[\_j1](../misc/bessel-functions-j0-j1-jn.md)|[sinh](../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)|  
|[copysign, copysignf, copysignl, \_copysign, \_copysignf, \_copysignl](../c-runtime-library/reference/copysign-copysignf-copysignl-copysign-copysignf-copysignl.md)|[\_jn](../misc/bessel-functions-j0-j1-jn.md)|[sqrt](../c-runtime-library/reference/sqrt-sqrtf-sqrtl.md)|  
|[cos](../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)|[ldexp](../c-runtime-library/reference/ldexp.md)|[\_status87, \_statusfp](../c-runtime-library/reference/status87-statusfp-statusfp2.md)|  
|[cosh](../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)|[log](../Topic/log,%20logf,%20log10,%20log10f.md)|[tan](../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)|  
|[Exp](../c-runtime-library/reference/exp-expf.md)|[log10](../Topic/log,%20logf,%20log10,%20log10f.md)|[tanh](../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)|  
|[fabs](../c-runtime-library/reference/fabs-fabsf-fabsl.md)|[\_logb](../c-runtime-library/reference/logb-logbf-logbl-logb-logbf.md)|[\_y0](../Topic/Bessel%20Functions:%20_y0,%20_y1,%20_yn.md)|  
|[\_finite](../c-runtime-library/reference/finite-finitef.md)|[longjmp](../c-runtime-library/reference/longjmp.md)|[\_y1](../Topic/Bessel%20Functions:%20_y0,%20_y1,%20_yn.md)|  
|[floor](../c-runtime-library/reference/floor-floorf-floorl.md)|[\_matherr](../c-runtime-library/reference/matherr.md)|[\_yn](../Topic/Bessel%20Functions:%20_y0,%20_y1,%20_yn.md)|  
|[fmod](../Topic/fmod,%20fmodf.md)|[modf](../c-runtime-library/reference/modf-modff-modfl.md)||  
  
 \* Хотя исходный код доступен для большей части из этой процедуры, он осуществляет внутренний вызов другой процедуры, для которой исходный код не предоставляется.  
  
 Некоторые функции времени выполнения C и операторы C\+\+ ведут себя иначе при их вызове из отладочного построения приложения. \(Обратите внимание, что отладочное построение приложения можно выполнить или определив флаг `_DEBUG`, или путем связывания с отладочной версией библиотеки времени выполнения C\). Различия в поведении обычно состоят из дополнительных функций или сведений, предоставленных процедурой для поддержки процесса отладки.  Эти процедуры перечислены в следующей таблице.  
  
### Процедуры, которые ведут себя по\-другому в отладочном построении приложения  
  
|||  
|-|-|  
|Процедура C [abort](../c-runtime-library/reference/abort.md)|C\+\+ [delete](../cpp/delete-operator-cpp.md) оператор|  
|Процедура C — [assert](../c-runtime-library/reference/assert-macro-assert-wassert.md)|C\+\+ [new](../cpp/new-operator-cpp.md) оператор|  
  
## См. также  
 [Процедуры среды выполнения по категориям](../c-runtime-library/run-time-routines-by-category.md)   
 [Проверка ошибок во время выполнения](../Topic/Run-Time%20Error%20Checking.md)