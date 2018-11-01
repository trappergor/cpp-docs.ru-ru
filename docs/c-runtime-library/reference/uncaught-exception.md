---
title: __uncaught_exception
ms.date: 11/04/2016
apiname:
- __uncaught_exception
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
- __uncaught_exception
helpviewer_keywords:
- __uncaught_exception
ms.assetid: 4d9b75c6-c9c7-4876-b761-ea9ab1925e96
ms.openlocfilehash: 19d1e18af27722d6f9da39ebaaf6c9415c281849
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50579638"
---
# <a name="uncaughtexception"></a>__uncaught_exception

Указывает, использует ли одно или несколько исключений возникло, но еще не были обработаны с помощью соответствующего **catch** блока [try-catch](../../cpp/try-throw-and-catch-statements-cpp.md) инструкции.

## <a name="syntax"></a>Синтаксис

```cpp
bool __uncaught_exception(
   );
```

## <a name="return-value"></a>Возвращаемое значение

**значение true,** от времени возникает исключение **попробуйте** блок до соответствующего **catch** блок инициализирован; в противном случае — значение **false**.

## <a name="remarks"></a>Примечания

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|__uncaught_exception|eh.h|

## <a name="see-also"></a>См. также

[Операторы try, throw и catch (C++)](../../cpp/try-throw-and-catch-statements-cpp.md)<br/>
