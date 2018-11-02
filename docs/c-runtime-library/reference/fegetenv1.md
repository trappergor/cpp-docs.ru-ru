---
title: fegetenv
ms.date: 04/05/2018
apiname:
- fetegenv
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- fegetenv
- fenv/fegetenv
helpviewer_keywords:
- fetegenv function
ms.assetid: 68962421-6978-4b27-8e4c-ad1577830cf6
ms.openlocfilehash: d3985e4dd2b3944bcdddb79605887def7ba15473
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50668095"
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

*penv*<br/>
Указатель на **fenv_t** объект, содержащий текущие значения среду с плавающей запятой.

## <a name="return-value"></a>Возвращаемое значение

Возвращает 0, если среду с плавающей запятой успешно сохранена в *penv*. В противном случае возвращается ненулевое значение.

## <a name="remarks"></a>Примечания

**Fegetenv** функция сохраняет текущую среду с плавающей запятой в объекте, на которые указывают *penv*. Среда с плавающей запятой представляет собой набор флагов состояний и режимов управления, влияющих на вычисления с плавающей запятой. Включает режим направления округления и флаги состояния для исключений с плавающей запятой.  Если *penv* не указывает на допустимый **fenv_t** объекта, последующее поведение не определено.

Чтобы использовать эту функцию, необходимо отключить оптимизацию вычислений с плавающей запятой, которая может препятствовать доступу. Для этого следует использовать директиву `#pragma fenv_access(on)` перед вызовом. Дополнительные сведения см. в разделе [fenv_access](../../preprocessor/fenv-access.md).

## <a name="requirements"></a>Требования

|Функция|Заголовок C|Заголовок C++|
|--------------|--------------|------------------|
|**fegetenv**|\<fenv.h>|\<cfenv>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Алфавитный указатель функций](crt-alphabetical-function-reference.md)<br/>
[fesetenv](fesetenv1.md)<br/>
