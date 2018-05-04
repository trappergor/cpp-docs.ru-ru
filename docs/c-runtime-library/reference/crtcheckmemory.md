---
title: _CrtCheckMemory | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _CrtCheckMemory
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
- CrtCheckMemory
- _CrtCheckMemory
dev_langs:
- C++
helpviewer_keywords:
- _CrtCheckMemory function
- CrtCheckMemory function
ms.assetid: 457cc72e-60fd-4177-ab5c-6ae26a420765
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0b6d4b84fd717525e7206956964204794fe6b88c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="crtcheckmemory"></a>_CrtCheckMemory

Проверяет целостность выделенных блоков памяти в отладочной куче (только в отладочной версии).

## <a name="syntax"></a>Синтаксис

```C

int _CrtCheckMemory( void );
```

## <a name="return-value"></a>Возвращаемое значение

В случае успешного выполнения **_CrtCheckMemory** возвращает значение TRUE; в противном случае функция возвращает значение FALSE.

## <a name="remarks"></a>Примечания

**_CrtCheckMemory** функция проверяет память, выделенную диспетчер отладочной кучи, проверяя базовой основной кучи и проверки каждого блока памяти. Если несогласованность памяти или ошибка произошла в базовой основной кучи сведения о заголовке отладки и буферы перезаписи **_CrtCheckMemory** создает отладочный отчет с информацией, описывающий условие ошибки. Когда [_DEBUG](../../c-runtime-library/debug.md) не определен, вызовы **_CrtCheckMemory** удаляются на этапе предварительной обработки.

Поведение **_CrtCheckMemory** можно управлять, задав битовые поля [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) флаг с помощью [_CrtSetDbgFlag](crtsetdbgflag.md) функции. Включение **_CRTDBG_CHECK_ALWAYS_DF** бит ON значений полей в **_CrtCheckMemory** будет вызываться каждый раз при запросе операции выделения памяти. Несмотря на то, что этот метод замедляет выполнение, он позволяет быстро перехватывать ошибки. Включение **_CRTDBG_ALLOC_MEM_DF** бит причины OFF поле **_CrtCheckMemory** не проверить кучи и сразу же возвращает **TRUE**.

Так как эта функция возвращает значение **TRUE** или **FALSE**, ее можно передать в один из макросов [_ASSERT](assert-asserte-assert-expr-macros.md) для создания простого механизма обработки ошибок отладки. Следующий пример вызывает сбой утверждения, если в куче обнаружено повреждение.

```C
_ASSERTE( _CrtCheckMemory( ) );
```

Дополнительные сведения о том, как **_CrtCheckMemory** можно использовать с другими отладочными функциями см. в разделе [функции создания отчетов о состоянии кучи](/visualstudio/debugger/crt-debug-heap-details). Общие сведения об управлении памятью и отладочной куче см. в разделе [Сведения о куче отладки CRT](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_CrtCheckMemory**|\<crtdbg.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Только отладочные версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Пример

Пример использования **_CrtCheckMemory**, в разделе [crt_dbg1](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg1).

## <a name="see-also"></a>См. также

[Процедуры отладки](../../c-runtime-library/debug-routines.md)<br/>
[_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)<br/>
[_CrtSetDbgFlag](crtsetdbgflag.md)<br/>
