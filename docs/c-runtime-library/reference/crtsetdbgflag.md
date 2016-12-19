---
title: "_CrtSetDbgFlag | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CrtSetDbgFlag"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_CRTDBG_REPORT_FLAG"
  - "_CRTDBG_CHECK_EVERY_16_DF"
  - "_CRTDBG_CHECK_DEFAULT_DF"
  - "CRTDBG_CHECK_DEFAULT_DF"
  - "CRTDBG_CHECK_EVERY_128_DF"
  - "CRTDBG_CHECK_EVERY_1024_DF"
  - "_CRTDBG_CHECK_EVERY_128_DF"
  - "CrtSetDbgFlag"
  - "CRTDBG_CHECK_EVERY_16_DF"
  - "_CRTDBG_CHECK_EVERY_1024_DF"
  - "_CrtSetDbgFlag"
  - "CRTDBG_REPORT_FLAG"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_CRTDBG_ALLOC_MEM_DF - макрос"
  - "_CRTDBG_CHECK_ALWAYS_DF - макрос"
  - "_CRTDBG_CHECK_CRT_DF - макрос"
  - "_CRTDBG_CHECK_DEFAULT_DF - макрос"
  - "_CRTDBG_CHECK_EVERY_1024_DF - макрос"
  - "_CRTDBG_CHECK_EVERY_128_DF - макрос"
  - "_CRTDBG_CHECK_EVERY_16_DF - макрос"
  - "_CRTDBG_DELAY_FREE_MEM_DF - макрос"
  - "_CRTDBG_REPORT_FLAG - макрос"
  - "_CrtSetDbgFlag - функция"
  - "CRTDBG_ALLOC_MEM_DF - макрос"
  - "CRTDBG_CHECK_ALWAYS_DF - макрос"
  - "CRTDBG_CHECK_CRT_DF - макрос"
  - "CRTDBG_CHECK_DEFAULT_DF - макрос"
  - "CRTDBG_CHECK_EVERY_1024_DF - макрос"
  - "CRTDBG_CHECK_EVERY_128_DF - макрос"
  - "CRTDBG_CHECK_EVERY_16_DF - макрос"
  - "CRTDBG_DELAY_FREE_MEM_DF - макрос"
  - "CRTDBG_REPORT_FLAG - макрос"
  - "CrtSetDbgFlag - функция"
ms.assetid: b5657ffb-6178-4cbf-9886-1af904ede94c
caps.latest.revision: 19
caps.handback.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _CrtSetDbgFlag
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Получает или изменяет состояние флага **\_crtDbgFlag** для управления поведением выделения памяти диспетчера отладочной кучи \(только отладочная версия\).  
  
## Синтаксис  
  
```  
  
int _CrtSetDbgFlag(     int newFlag  );  
```  
  
#### Параметры  
 `newFlag`  
 Новое состояние для **\_crtDbgFlag**.  
  
## Возвращаемое значение  
 Возвращает предыдущее состояние **\_crtDbgFlag**.  
  
## Заметки  
 Функция `_CrtSetDbgFlag` позволяет приложению контролировать, каким образом диспетчер отладочной кучи будет отслеживать выделение памяти, путем изменения битовых полей флага **\_crtDbgFlag**.  Задавая биты \(включение\), приложение может настраивать выполнение диспетчером отладочной кучи определенных операций отладки, включая проверку утечек памяти при завершении работы приложения и создание отчетов о найденных утечках, моделирование условий недостатка памяти \(указывая, что освобожденные блоки памяти должны оставаться в связанном списке кучи\) и проверку целостности кучи \(путем проверки каждого блока памяти в каждом запросе на выделение\).  Если [\_DEBUG](../Topic/_DEBUG.md) не определен, вызовы `_CrtSetDbgFlag` удаляются на этапе предварительной обработки.  
  
 В следующей таблице перечислены битовые поля для флага **\_crtDbgFlag** с описанием их поведения.  Поскольку задание бит влечет за собой увеличение объема диагностических данных и снижение скорости выполнения программы, по умолчанию они не заданы \(выключены\).  Дополнительные сведения об этих битовых полях см. в разделе [Функции создания отчетов о состоянии кучи](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Heap_State_Reporting_Functions).  
  
|Битовое поле|По умолчанию|Описание|  
|------------------|------------------|--------------|  
|**\_CRTDBG\_ALLOC\_MEM\_DF**|ON|ON: включение выделения памяти отладочной кучи и использование идентификаторов типов блоков памяти, таких как `_CLIENT_BLOCK`.  OFF: добавление новых выделений в связанный список кучи; однако в качестве типа блока задается **\_IGNORE\_BLOCK**.<br /><br /> Может также быть совмещено с любыми макросами частоты проверки кучи.|  
|**\_CRTDBG\_CHECK\_ALWAYS\_DF**|OFF|ON: вызов [\_CrtCheckMemory](../../c-runtime-library/reference/crtcheckmemory.md) при каждом запросе на выделение и отмену выделения.  OFF: `_CrtCheckMemory` необходимо вызывать явно.<br /><br /> Макросы частоты проверки кучи не действуют, если задан этот флаг.|  
|`_CRTDBG_CHECK_CRT_DF`|OFF|ON: включение типов `_CRT_BLOCK` в операции обнаружения утечек и разницы состояния памяти.  OFF: память, используемая внутренне библиотекой времени выполнения, игнорируется этими операциями.<br /><br /> Может также быть совмещено с любыми макросами частоты проверки кучи.|  
|**\_CRTDBG\_DELAY\_FREE\_MEM\_DF**|OFF|ON: хранение освободившихся блоков памяти в связанном списке кучи, назначение им типа **\_FREE\_BLOCK** и их заполнение байтовым значением 0xDD.  OFF: освободившиеся блоки не хранятся в связанном списке кучи.<br /><br /> Может также быть совмещено с любыми макросами частоты проверки кучи.|  
|`_CRTDBG_LEAK_CHECK_DF`|OFF|ON: выполнение автоматической проверки утечки при завершении работы программы путем вызова функции [\_CrtDumpMemoryLeaks](../../c-runtime-library/reference/crtdumpmemoryleaks.md) и создания отчета об ошибке, если приложению не удалось освободить всю выделенную ему память.  OFF: автоматическая проверка утечки при завершении работы программы не выполняется.<br /><br /> Может также быть совмещено с любыми макросами частоты проверки кучи.|  
  
 **Макросы частоты проверки кучи**  
  
 Можно указать, как часто библиотека времени выполнения языка C будет выполнять проверку отладочной кучи \(`_CrtCheckMemory`\) на основе числа вызовов макросов `malloc`, `realloc`, **free** и `_msize`.  
  
 Затем `_CrtSetDbgFlag` проверяет верхние 16 бит параметра `newFlag`, чтобы получить значение.  Указанное значение представляет собой число вызовов `malloc`, `realloc`, **free** и `_msize` между вызовами `_CrtCheckMemory`.  Для этой цели предоставляется четыре готовых макроса.  
  
|Макрос|Число вызовов malloc, realloc, free и \_msize между вызовами функции \_CrtCheckMemory|  
|------------|-------------------------------------------------------------------------------------------|  
|\_CRTDBG\_CHECK\_EVERY\_16\_DF|16|  
|\_CRTDBG\_CHECK\_EVERY\_128\_DF|128|  
|\_CRTDBG\_CHECK\_EVERY\_1024\_DF|1024|  
|\_CRTDBG\_CHECK\_DEFAULT\_DF|0 \(по умолчанию проверки кучи не выполняются\)|  
  
 По умолчанию функция `_CrtCheckMemory` вызывается один раз на 1024 вызова `malloc`, `realloc`, **free** и `_msize`.  
  
 Например, можно задать проверку кучи каждые 16 операций `malloc`, `realloc`, **free** и `_msize`, используя следующий код.  
  
```  
#include <crtdbg.h>  
int main( )  
{  
int tmp;  
  
// Get the current bits  
tmp = _CrtSetDbgFlag(_CRTDBG_REPORT_FLAG);  
  
// Clear the upper 16 bits and OR in the desired freqency  
tmp = (tmp & 0x0000FFFF) | _CRTDBG_CHECK_EVERY_16_DF;  
  
// Set the new bits  
_CrtSetDbgFlag(tmp);  
}  
```  
  
 Верхние 16 бит параметра `newFlag` пропускаются, если указан флаг \_CRTDBG\_CHECK\_ALWAYS\_DF.  В этом случае функция `_CrtCheckMemory` вызывается при каждом вызове `malloc`, `realloc`, **free** и `_msize`.  
  
 `newFlag` — это новое состояние, применяемое к **\_crtDbgFlag**, которое является комбинацией значений для каждого из битовых полей.  
  
### Изменение одного или более битовых полей и создание нового состояния флага  
  
1.  Вызовите `_CrtSetDbgFlag` с параметром `newFlag`, равным `_CRTDBG_REPORT_FLAG`, чтобы получить текущее состояние флага **\_crtDbgFlag** и сохранить возвращенное значение во временной переменной.  
  
2.  Включите любые биты, применив оператор `OR` для этой временной переменной и соответствующей битовой маски \(представленной в коде приложения константой манифеста\).  
  
3.  Отключите остальные биты, применив оператор **AND** для переменной и соответствующей битовой маски, инвертированной с помощью битового оператора **NOT**.  
  
4.  Вызовите функцию `_CrtSetDbgFlag` с параметром `newFlag`, равным значению, хранимому во временной переменной, чтобы задать новое состояние **\_crtDbgFlag**.  
  
 Следующий пример кода демонстрирует моделирование условий недостатка памяти путем хранения освободившихся блоков памяти в связанном списке кучи и запрета вызова `_CrtCheckMemory` при каждом запросе выделения.  
  
```  
// Get the current state of the flag  
// and store it in a temporary variable  
int tmpFlag = _CrtSetDbgFlag( _CRTDBG_REPORT_FLAG );  
  
// Turn On (OR) - Keep freed memory blocks in the  
// heap's linked list and mark them as freed  
tmpFlag |= _CRTDBG_DELAY_FREE_MEM_DF;  
  
// Turn Off (AND) - prevent _CrtCheckMemory from  
// being called at every allocation request  
tmpFlag &= ~_CRTDBG_CHECK_ALWAYS_DF;  
  
// Set the new state for the flag  
_CrtSetDbgFlag( tmpFlag );  
```  
  
 Обзор отладочной кучи и управления памятью см. в разделе [Сведения о куче отладки CRT](../Topic/CRT%20Debug%20Heap%20Details.md).  
  
 Чтобы отключить флаг с помощью функции `_CrtSetDbgFlag`, необходимо применить операцию **AND** к переменной и соответствующей битовой маске, инвертированной с помощью **NOT**.  
  
 Если `newFlag` не является допустимым числом, эта функция вызывает обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если выполнение может быть продолжено, эта функция задает для `errno` значение `EINVAL` и возвращает предыдущее состояние `_crtDbgFlag`.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_CrtSetDbgFlag`|\<crtdbg.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Библиотеки  
 Только отладочные версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
## Пример  
  
```  
// crt_crtsetdflag.c  
// compile with: /c -D_DEBUG /MTd -Od -Zi -W3 /link -verbose:lib /debug  
/*  
 * This program concentrates on allocating and freeing memory  
 * blocks to test the functionality of the _crtDbgFlag flag..  
 */  
  
#include <string.h>  
#include <malloc.h>  
#include <crtdbg.h>  
  
int main( )  
{  
        char *p1, *p2;  
        int tmpDbgFlag;  
  
        _CrtSetReportMode( _CRT_ERROR, _CRTDBG_MODE_FILE );  
        _CrtSetReportFile( _CRT_ERROR, _CRTDBG_FILE_STDERR );  
        /*  
         * Set the debug-heap flag to keep freed blocks in the  
         * heap's linked list - This will allow us to catch any  
         * inadvertent use of freed memory  
         */  
        tmpDbgFlag = _CrtSetDbgFlag(_CRTDBG_REPORT_FLAG);  
        tmpDbgFlag |= _CRTDBG_DELAY_FREE_MEM_DF;  
        tmpDbgFlag |= _CRTDBG_LEAK_CHECK_DF;  
        _CrtSetDbgFlag(tmpDbgFlag);  
  
        /*  
         * Allocate 2 memory blocks and store a string in each  
         */  
        p1 = malloc( 34 );  
        p2 = malloc( 38 );  
        strcpy_s( p1, 34, "p1 points to a Normal allocation block" );  
        strcpy_s( p2, 38, "p2 points to a Client allocation block" );  
  
        /*  
         * Free both memory blocks  
         */  
        free( p2 );  
        free( p1 );  
  
        /*  
         * Set the debug-heap flag to no longer keep freed blocks in the  
         * heap's linked list and turn on Debug type allocations (CLIENT)  
         */  
        tmpDbgFlag = _CrtSetDbgFlag(_CRTDBG_REPORT_FLAG);  
        tmpDbgFlag |= _CRTDBG_ALLOC_MEM_DF;  
        tmpDbgFlag &= ~_CRTDBG_DELAY_FREE_MEM_DF;  
        _CrtSetDbgFlag(tmpDbgFlag);  
  
        /*  
         * Explicitly call _malloc_dbg to obtain the filename and   
         * line number of our allocation request and also so we can   
         * allocate CLIENT type blocks specifically for tracking  
         */  
        p1 = _malloc_dbg( 40, _NORMAL_BLOCK, __FILE__, __LINE__ );  
        p2 = _malloc_dbg( 40, _CLIENT_BLOCK, __FILE__, __LINE__ );  
        strcpy_s( p1, 40, "p1 points to a Normal allocation block" );  
        strcpy_s( p2, 40, "p2 points to a Client allocation block" );  
  
        /*  
         * _free_dbg must be called to free the CLIENT block  
         */  
        _free_dbg( p2, _CLIENT_BLOCK );  
        free( p1 );  
  
        /*  
         * Allocate p1 again and then exit - this will leave unfreed  
         * memory on the heap  
         */  
        p1 = malloc( 10 );  
}  
```  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Процедуры отладки](../../c-runtime-library/debug-routines.md)   
 [\_crtDbgFlag](../Topic/_crtDbgFlag.md)   
 [\_CrtCheckMemory](../../c-runtime-library/reference/crtcheckmemory.md)