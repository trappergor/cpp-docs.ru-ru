---
title: fegetenv
ms.date: 04/05/2018
api_name:
- fetegenv
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
- fegetenv
- fenv/fegetenv
helpviewer_keywords:
- fetegenv function
ms.assetid: 68962421-6978-4b27-8e4c-ad1577830cf6
ms.openlocfilehash: b2e3566eb96174d0f0ccd6beb401824cc052c995
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70941246"
---
# <a name="fegetenv"></a>fegetenv

Сохраняет текущую среду с плавающей запятой в указанном объекте.

## <a name="syntax"></a>Синтаксис

```C
int fegetenv(
   fenv_t *penv
);
```

### <a name="parameters"></a>Параметры

*пенв*<br/>
Указатель на объект **fenv_t** , который будет содержать текущие значения среды с плавающей запятой.

## <a name="return-value"></a>Возвращаемое значение

Возвращает 0, если среда с плавающей точкой успешно сохранена в *пенв*. В противном случае возвращается ненулевое значение.

## <a name="remarks"></a>Примечания

Функция **fegetenv** сохраняет текущую среду с плавающей запятой в объекте, на который указывает *пенв*. Среда с плавающей запятой представляет собой набор флагов состояний и режимов управления, влияющих на вычисления с плавающей запятой. Включает режим направления округления и флаги состояния для исключений с плавающей запятой.  Если *пенв* не указывает на допустимый объект **fenv_t** , последующее поведение не определено.

Чтобы использовать эту функцию, необходимо отключить оптимизацию вычислений с плавающей запятой, которая может препятствовать доступу. Для этого следует использовать директиву `#pragma fenv_access(on)` перед вызовом. Дополнительные сведения см. в разделе [fenv_access](../../preprocessor/fenv-access.md).

## <a name="requirements"></a>Требования

|Функция|Заголовок C|Заголовок C++|
|--------------|--------------|------------------|
|**fegetenv**|\<fenv.h>|\<cfenv>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Алфавитный указатель функций](crt-alphabetical-function-reference.md)<br/>
[fesetenv](fesetenv1.md)<br/>
