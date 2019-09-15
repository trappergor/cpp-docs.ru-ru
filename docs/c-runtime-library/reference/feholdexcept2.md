---
title: feholdexcept
ms.date: 04/05/2018
api_name:
- feholdexcept
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
- api-ms-win-crt-runtime-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- feholdexcept
- fenv/feholdexcept
helpviewer_keywords:
- feholdexcept function
ms.assetid: 88e512ae-b5d8-452c-afe9-c824cd3ef1d8
ms.openlocfilehash: bd55a4ed627d731f7246d589d4b74b4173e31d4e
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70941192"
---
# <a name="feholdexcept"></a>feholdexcept

Сохраняет текущую среду с плавающей запятой в указанном объекте, очищает флаги состояний с плавающей запятой и, если это возможно, переводит среду с плавающей запятой в режим без остановки.

## <a name="syntax"></a>Синтаксис

```C
int feholdexcept(
   fenv_t *penv
);
```

### <a name="parameters"></a>Параметры

*пенв*<br/>
Указатель на объект **fenv_t** , который будет содержать копию среды с плавающей запятой.

## <a name="return-value"></a>Возвращаемое значение

Возвращает нуль только в том случае, если функция может успешно включить неостанавливаемую обработку исключений с плавающей точкой.

## <a name="remarks"></a>Примечания

Функция **feholdexcept** используется для хранения состояния текущей среды с плавающей точкой в объекте **fenv_t** , на который указывает *пенв*, и для установки среды, чтобы не прерывать выполнение при исключениях с плавающей запятой. Это называется режимом без остановки.  В этом режиме работа продолжается, пока среда не будет восстановлена с помощью функции [fesetenv](fesetenv1.md) или [feupdateenv](feupdateenv.md).

Эту функцию можно использовать в начале подпрограммы, который должна скрывать от вызывающей стороны одно или несколько исключений с плавающей запятой. Чтобы сообщить об исключении, можно просто удалить ненужные исключения с помощью [феклеарексцепт,](feclearexcept1.md) а затем завершить режим, не являющийся остановкой, с вызовом **feupdateenv**.

Чтобы использовать эту функцию, необходимо отключить оптимизацию вычислений с плавающей запятой, которая может препятствовать доступу. Для этого следует использовать директиву `#pragma fenv_access(on)` перед вызовом. Дополнительные сведения см. в разделе [fenv_access](../../preprocessor/fenv-access.md).

## <a name="requirements"></a>Требования

|Функция|Заголовок C|Заголовок C++|
|--------------|--------------|------------------|
|**feholdexcept**|\<fenv.h>|\<cfenv>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Алфавитный указатель функций](crt-alphabetical-function-reference.md)<br/>
[feclearexcept](feclearexcept1.md)<br/>
[fesetenv](fesetenv1.md)<br/>
[feupdateenv](feupdateenv.md)<br/>
