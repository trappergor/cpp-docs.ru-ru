---
title: _CrtSetDbgFlag | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _CrtSetDbgFlag
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- _CRTDBG_REPORT_FLAG
- _CRTDBG_CHECK_EVERY_16_DF
- _CRTDBG_CHECK_DEFAULT_DF
- CRTDBG_CHECK_DEFAULT_DF
- CRTDBG_CHECK_EVERY_128_DF
- CRTDBG_CHECK_EVERY_1024_DF
- _CRTDBG_CHECK_EVERY_128_DF
- CrtSetDbgFlag
- CRTDBG_CHECK_EVERY_16_DF
- _CRTDBG_CHECK_EVERY_1024_DF
- _CrtSetDbgFlag
- CRTDBG_REPORT_FLAG
dev_langs:
- C++
helpviewer_keywords:
- _CRTDBG_CHECK_EVERY_16_DF macro
- CRTDBG_CHECK_EVERY_16_DF macro
- _CRTDBG_CHECK_ALWAYS_DF macro
- _CRTDBG_CHECK_DEFAULT_DF macro
- CRTDBG_ALLOC_MEM_DF macro
- CRTDBG_CHECK_ALWAYS_DF macro
- _CRTDBG_ALLOC_MEM_DF macro
- _CRTDBG_REPORT_FLAG macro
- _CRTDBG_CHECK_EVERY_128_DF macro
- CRTDBG_REPORT_FLAG macro
- _CRTDBG_CHECK_EVERY_1024_DF macro
- CRTDBG_CHECK_DEFAULT_DF macro
- CRTDBG_CHECK_EVERY_1024_DF macro
- _CrtSetDbgFlag function
- CrtSetDbgFlag function
- _CRTDBG_DELAY_FREE_MEM_DF macro
- CRTDBG_CHECK_EVERY_128_DF macro
- CRTDBG_DELAY_FREE_MEM_DF macro
- CRTDBG_CHECK_CRT_DF macro
- _CRTDBG_CHECK_CRT_DF macro
ms.assetid: b5657ffb-6178-4cbf-9886-1af904ede94c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 413504d8941aab1585ff03d361f8081fef4529a2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="crtsetdbgflag"></a>_CrtSetDbgFlag

Получает или изменяет состояние флага **_crtDbgFlag** для управления поведением выделения памяти диспетчера отладочной кучи (только отладочная версия).

## <a name="syntax"></a>Синтаксис

```C
int _CrtSetDbgFlag(
   int newFlag
);
```

### <a name="parameters"></a>Параметры

*newFlag*<br/>
Новое состояние для **_crtDbgFlag**.

## <a name="return-value"></a>Возвращаемое значение

Возвращает предыдущее состояние **_crtDbgFlag**.

## <a name="remarks"></a>Примечания

**_CrtSetDbgFlag** функция позволяет приложению контролировать, каким образом диспетчер отладочной кучи будет отслеживать выделение памяти путем изменения битовых полей **_crtDbgFlag** флаг. Задавая биты (включение), приложение может настраивать выполнение диспетчером отладочной кучи определенных операций отладки, включая проверку утечек памяти при завершении работы приложения и создание отчетов о найденных утечках, моделирование условий недостатка памяти (указывая, что освобожденные блоки памяти должны оставаться в связанном списке кучи) и проверку целостности кучи (путем проверки каждого блока памяти в каждом запросе на выделение). Когда [_DEBUG](../../c-runtime-library/debug.md) не определен, вызовы **_CrtSetDbgFlag** удаляются на этапе предварительной обработки.

В следующей таблице перечислены битовые поля для флага **_crtDbgFlag** с описанием их поведения. Поскольку задание бит влечет за собой увеличение объема диагностических данных и снижение скорости выполнения программы, по умолчанию они не заданы (выключены). Дополнительные сведения об этих битовых полях см. в разделе [Функции создания отчетов о состоянии кучи](/visualstudio/debugger/crt-debug-heap-details).

|Битовое поле|По умолчанию|Описание|
|---------------|-------------|-----------------|
|**_CRTDBG_ALLOC_MEM_DF**|ON|ON: Включение выделения памяти отладочной кучи и использование идентификаторов типов блоков памяти, такие как **_CLIENT_BLOCK**. OFF: добавление новых выделений в связанный список кучи; однако в качестве типа блока задается **_IGNORE_BLOCK**.<br /><br /> Может также быть совмещено с любыми макросами частоты проверки кучи.|
|**_CRTDBG_CHECK_ALWAYS_DF**|OFF|ON: вызов [_CrtCheckMemory](crtcheckmemory.md) при каждом запросе на выделение и отмену выделения. OFF: **_CrtCheckMemory** должен вызываться явным образом.<br /><br /> Макросы частоты проверки кучи не действуют, если задан этот флаг.|
|**_CRTDBG_CHECK_CRT_DF**|OFF|ON: Включение **_CRT_BLOCK** типов в состоянии обнаружения и памяти утечки разница операций. OFF: память, используемая внутренне библиотекой времени выполнения, игнорируется этими операциями.<br /><br /> Может также быть совмещено с любыми макросами частоты проверки кучи.|
|**_CRTDBG_DELAY_FREE_MEM_DF**|OFF|ON: хранение освободившихся блоков памяти в связанном списке кучи, назначение им типа **_FREE_BLOCK** и их заполнение байтовым значением 0xDD. OFF: освободившиеся блоки не хранятся в связанном списке кучи.<br /><br /> Может также быть совмещено с любыми макросами частоты проверки кучи.|
|**_CRTDBG_LEAK_CHECK_DF**|OFF|ON: выполнение автоматической проверки утечки при завершении работы программы путем вызова функции [_CrtDumpMemoryLeaks](crtdumpmemoryleaks.md) и создания отчета об ошибке, если приложению не удалось освободить всю выделенную ему память. OFF: автоматическая проверка утечки при завершении работы программы не выполняется.<br /><br /> Может также быть совмещено с любыми макросами частоты проверки кучи.|

**Макросы частоты проверки кучи**

Можно указать, как часто библиотека времени выполнения C будет выполнять проверку отладочной кучи (**_CrtCheckMemory**) на основе числа вызовов **malloc**, **realloc**, **свободного**, и **_msize**.

**_CrtSetDbgFlag** затем проверяет верхние 16 бит *newFlag* параметра для значения. Указанное значение число **malloc**, **realloc**, **свободного**, и **_msize** вызывает между **_CrtCheckMemory**  вызовов. Для этой цели предоставляется четыре готовых макроса.

|Макрос|Число вызовов malloc, realloc, free и _msize между вызовами функции _CrtCheckMemory|
|-----------|------------------------------------------------------------------------------------------|
|_CRTDBG_CHECK_EVERY_16_DF|16|
|_CRTDBG_CHECK_EVERY_128_DF|128|
|_CRTDBG_CHECK_EVERY_1024_DF|1024|
|_CRTDBG_CHECK_DEFAULT_DF|0 (по умолчанию проверки кучи не выполняются)|

По умолчанию **_CrtCheckMemory** вызывается один раз каждые 1024 вызова **malloc**, **realloc**, **свободного**, и **_ msize**.

Например, можно указать проверку кучи каждые 16 **malloc**, **realloc**, **свободного**, и **_msize** операции с помощью следующего кода:

```C
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

Верхние 16 бит *newFlag* параметр игнорируются, если указан флаг _crtdbg_check_always_df. В этом случае **_CrtCheckMemory** вызывается каждый раз при вызове **malloc**, **realloc**, **свободного**, и **_msize**.

*newFlag* — это новое состояние для применения к **_crtDbgFlag** и представляет собой сочетание значений для каждого из битовых полей.

### <a name="to-change-one-or-more-of-these-bit-fields-and-create-a-new-state-for-the-flag"></a>Изменение одного или более битовых полей и создание нового состояния флага

1. Вызовите **_CrtSetDbgFlag** с *newFlag* равно **_CRTDBG_REPORT_FLAG** для получения текущего **_crtDbgFlag** состояния и хранения Возвращенное значение во временной переменной.

1. Включите любые биты, битовую **или** временной переменной и соответствующей битовой маски (представленной в коде приложения константой манифеста).

1. Отключите остальные биты, применив оператор **AND** для переменной и соответствующей битовой маски, инвертированной с помощью битового оператора **NOT**.

1. Вызовите **_CrtSetDbgFlag** с *newFlag* равно значению, хранящиеся в этой временной переменной, чтобы задать новое состояние для **_crtDbgFlag**.

В следующем коде показано, как моделировать нехватки памяти условия путем хранения освободившихся блоков памяти в связанном списке отладочной кучи и предотвратить **_CrtCheckMemory** вызова при каждом запросе выделения:

```C
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

Общие сведения об управлении памятью и отладочной куче см. в разделе [Сведения о куче отладки CRT](/visualstudio/debugger/crt-debug-heap-details).

Чтобы отключить флаг с **_CrtSetDbgFlag** функция, должен **AND** переменной побитовым **не** битовой маской.

Если *newFlag* не является допустимым значением, эта функция вызывает обработчик недопустимого параметра, как описано в [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эта функция задает **errno** для **EINVAL** и возвращает предыдущее состояние **_crtDbgFlag**.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_CrtSetDbgFlag**|\<crtdbg.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Только отладочные версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Пример

```C
// crt_crtsetdflag.c
// compile with: /c -D_DEBUG /MTd -Od -Zi -W3 /link -verbose:lib /debug

// This program concentrates on allocating and freeing memory
// blocks to test the functionality of the _crtDbgFlag flag.

#include <string.h>
#include <malloc.h>
#include <crtdbg.h>

int main( )
{
    char *p1, *p2;
    int tmpDbgFlag;

    _CrtSetReportMode( _CRT_ERROR, _CRTDBG_MODE_FILE );
    _CrtSetReportFile( _CRT_ERROR, _CRTDBG_FILE_STDERR );

    // Set the debug-heap flag to keep freed blocks in the
    // heap's linked list - This will allow us to catch any
    // inadvertent use of freed memory
    tmpDbgFlag = _CrtSetDbgFlag(_CRTDBG_REPORT_FLAG);
    tmpDbgFlag |= _CRTDBG_DELAY_FREE_MEM_DF;
    tmpDbgFlag |= _CRTDBG_LEAK_CHECK_DF;
    _CrtSetDbgFlag(tmpDbgFlag);

    // Allocate 2 memory blocks and store a string in each
    p1 = malloc( 34 );
    p2 = malloc( 38 );
    strcpy_s( p1, 34, "p1 points to a Normal allocation block" );
    strcpy_s( p2, 38, "p2 points to a Client allocation block" );

    // Free both memory blocks
    free( p2 );
    free( p1 );

    // Set the debug-heap flag to no longer keep freed blocks in the
    // heap's linked list and turn on Debug type allocations (CLIENT)
    tmpDbgFlag = _CrtSetDbgFlag(_CRTDBG_REPORT_FLAG);
    tmpDbgFlag |= _CRTDBG_ALLOC_MEM_DF;
    tmpDbgFlag &= ~_CRTDBG_DELAY_FREE_MEM_DF;
    _CrtSetDbgFlag(tmpDbgFlag);

    // Explicitly call _malloc_dbg to obtain the filename and
    // line number of our allocation request and also so we can
    // allocate CLIENT type blocks specifically for tracking
    p1 = _malloc_dbg( 40, _NORMAL_BLOCK, __FILE__, __LINE__ );
    p2 = _malloc_dbg( 40, _CLIENT_BLOCK, __FILE__, __LINE__ );
    strcpy_s( p1, 40, "p1 points to a Normal allocation block" );
    strcpy_s( p2, 40, "p2 points to a Client allocation block" );

    // _free_dbg must be called to free the CLIENT block
    _free_dbg( p2, _CLIENT_BLOCK );
    free( p1 );

    // Allocate p1 again and then exit - this will leave unfreed
    // memory on the heap
    p1 = malloc( 10 );
}
```

## <a name="see-also"></a>См. также

[Процедуры отладки](../../c-runtime-library/debug-routines.md)<br/>
[_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)<br/>
[_CrtCheckMemory](crtcheckmemory.md)<br/>
