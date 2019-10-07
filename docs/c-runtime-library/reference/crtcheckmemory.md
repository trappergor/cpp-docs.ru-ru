---
title: _CrtCheckMemory
ms.date: 11/04/2016
api_name:
- _CrtCheckMemory
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- CrtCheckMemory
- _CrtCheckMemory
helpviewer_keywords:
- _CrtCheckMemory function
- CrtCheckMemory function
ms.assetid: 457cc72e-60fd-4177-ab5c-6ae26a420765
ms.openlocfilehash: 7e458825a81b7032310458ccda52d9299e126a35
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70938863"
---
# <a name="_crtcheckmemory"></a>_CrtCheckMemory

Проверяет целостность выделенных блоков памяти в отладочной куче (только в отладочной версии).

## <a name="syntax"></a>Синтаксис

```C

int _CrtCheckMemory( void );
```

## <a name="return-value"></a>Возвращаемое значение

В случае успеха **_CrtCheckMemory** возвращает значение true; в противном случае функция возвращает значение FALSE.

## <a name="remarks"></a>Примечания

Функция **_CrtCheckMemory** проверяет память, выделенную диспетчером отладочной кучи, проверяя базовую кучу и проверяя каждый блок памяти. Если ошибка или несоответствие памяти обнаружены в базовой куче, сведениях заголовка отладки или буферах перезаписи, **_CrtCheckMemory** создает отчет об отладке с информацией, описывающей условие ошибки. Если [_DEBUG](../../c-runtime-library/debug.md) не определен, вызовы **_CrtCheckMemory** удаляются во время предварительной обработки.

Поведение **_CrtCheckMemory** можно контролировать путем установки битовых полей флага [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) с помощью функции [_CrtSetDbgFlag](crtsetdbgflag.md) . Включение битового поля **_CRTDBG_CHECK_ALWAYS_DF** в результате **_CrtCheckMemory** вызывается каждый раз, когда запрашивается операция выделения памяти. Несмотря на то, что этот метод замедляет выполнение, он позволяет быстро перехватывать ошибки. Отключение битового поля **_CRTDBG_ALLOC_MEM_DF** приводит к тому, что **_CrtCheckMemory** не проверяет кучу и немедленно возвращает **значение true**.

Так как эта функция возвращает значение **TRUE** или **FALSE**, ее можно передать в один из макросов [_ASSERT](assert-asserte-assert-expr-macros.md) для создания простого механизма обработки ошибок отладки. Следующий пример вызывает сбой утверждения, если в куче обнаружено повреждение.

```C
_ASSERTE( _CrtCheckMemory( ) );
```

Дополнительные сведения о том, как **_CrtCheckMemory** можно использовать с другими функциями отладки, см. в разделе [функции создания отчетов о состоянии кучи](/visualstudio/debugger/crt-debug-heap-details). Общие сведения об управлении памятью и отладочной куче см. в разделе [Сведения о куче отладки CRT](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_CrtCheckMemory**|\<crtdbg.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Только отладочные версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Пример

Пример использования **_CrtCheckMemory**см. в разделе [crt_dbg1](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg1).

## <a name="see-also"></a>См. также

[Процедуры отладки](../../c-runtime-library/debug-routines.md)<br/>
[_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)<br/>
[_CrtSetDbgFlag](crtsetdbgflag.md)<br/>
