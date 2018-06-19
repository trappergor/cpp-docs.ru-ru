---
title: _CrtDbgBreak | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _CrtDbgBreak
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
- _CrtDbgBreak
- CrtDbgBreak
dev_langs:
- C++
helpviewer_keywords:
- CrtDbgBreak function
- _CrtDbgBreak function
ms.assetid: 01f8b4a2-a2c7-4e1f-9f39-e573b4a7871f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2141b3c70755eb03e77c8f66feed482b5e86b529
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32394055"
---
# <a name="crtdbgbreak"></a>_CrtDbgBreak

Устанавливает точку останова в определенной строке кода. (Используется только в режиме отладки.)

## <a name="syntax"></a>Синтаксис

```C
void _CrtDbgBreak( void );
```

## <a name="return-value"></a>Возвращаемое значение

Возвращаемое значение отсутствует.

## <a name="remarks"></a>Примечания

**_CrtDbgBreak** функция задает точку останова для отладки в конкретной строке кода котором эта функция находится. Эта функция используется в режиме отладки только и зависит от **_DEBUG** предварительного определения.

Дополнительные сведения о других допускающих подключение функциях среды выполнения и написании собственных определяемых клиентом функциях-ловушках см. в разделе [Запись собственных функций отладочных ловушек](/visualstudio/debugger/debug-hook-function-writing).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_CrtDbgBreak**|\<CRTDBG.h>|

## <a name="libraries"></a>Библиотеки

Только отладочные версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>См. также

[Процедуры отладки](../../c-runtime-library/debug-routines.md)<br/>
[__debugbreak](../../intrinsics/debugbreak.md)<br/>
