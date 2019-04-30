---
title: fesetenv
ms.date: 04/05/2018
apiname:
- fesetenv
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
- fesetenv
- fenv/fesetenv
helpviewer_keywords:
- fesetenv function
ms.assetid: ffc64fff-8ea7-4d59-9e04-ff96ef8cd012
ms.openlocfilehash: 8c91bfbb89df964fed0a632d5fb5ebac47ebe948
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62334200"
---
# <a name="fesetenv"></a>fesetenv

Задает текущую среду с плавающей запятой.

## <a name="syntax"></a>Синтаксис

```C
int fesetenv(
   const fenv_t *penv
);
```

### <a name="parameters"></a>Параметры

*penv*<br/>
Указатель на **fenv_t** объект, который содержит среду с плавающей запятой в качестве набора путем вызова [fegetenv](fegetenv1.md) или [feholdexcept](feholdexcept2.md). Можно также указать среду с плавающей запятой по умолчанию с помощью **FE_DFL_ENV** макрос.

## <a name="return-value"></a>Возвращаемое значение

Возвращает 0, если среда был успешно установлена. В противном случае возвращается ненулевое значение.

## <a name="remarks"></a>Примечания

**Fesetenv** функция задает текущую среду с плавающей запятой из значения, хранящегося в **fenv_t** объекта, на который указывает *penv*. Среда с плавающей запятой представляет собой набор флагов состояний и режимов управления, влияющих на вычисления с плавающей запятой. Включает режим округления и флаги состояния для исключений с плавающей запятой.  Если *penv* не **FE_DFL_ENV** или не указывает на допустимый **fenv_t** объекта, последующее поведение не определено.

Вызов этой функции задает исключение флаги состояния, которые находятся в *penv* объект, но он не вызывает эти исключения.

Чтобы использовать эту функцию, необходимо отключить оптимизацию вычислений с плавающей запятой, которая может препятствовать доступу. Для этого следует использовать директиву `#pragma fenv_access(on)` перед вызовом. Дополнительные сведения см. в разделе [fenv_access](../../preprocessor/fenv-access.md).

## <a name="requirements"></a>Требования

|Функция|Заголовок C|Заголовок C++|
|--------------|--------------|------------------|
|**fesetenv**|\<fenv.h>|\<cfenv>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Алфавитный указатель функций](crt-alphabetical-function-reference.md)<br/>
[fegetenv](fegetenv1.md)<br/>
[feclearexcept](feclearexcept1.md)<br/>
[feholdexcept](feholdexcept2.md)<br/>
[fesetexceptflag](fesetexceptflag2.md)<br/>
