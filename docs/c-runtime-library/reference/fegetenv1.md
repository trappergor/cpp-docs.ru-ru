---
title: fegetenv | Документы Microsoft
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- fetegenv function
ms.assetid: 68962421-6978-4b27-8e4c-ad1577830cf6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fc8b5d189838c2788bc6200f9072c9511e61d42f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
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
Указатель на **fenv_t** объект, содержащий текущие значения с плавающей запятой среды.

## <a name="return-value"></a>Возвращаемое значение

Возвращает 0, если в среде с плавающей запятой было успешно сохранено в *penv*. В противном случае возвращается ненулевое значение.

## <a name="remarks"></a>Примечания

**Fegetenv** функция сохраняет текущую среду с плавающей запятой в объекте, на который указывает *penv*. Среда с плавающей запятой представляет собой набор флагов состояний и режимов управления, влияющих на вычисления с плавающей запятой. Включает режим направления округления и флаги состояния для исключений с плавающей запятой.  Если *penv* не указывает на допустимый **fenv_t** объекта, последующее поведение не определено.

Чтобы использовать эту функцию, необходимо отключить оптимизацию вычислений с плавающей запятой, которая может препятствовать доступу. Для этого следует использовать директиву `#pragma fenv_access(on)` перед вызовом. Дополнительные сведения см. в разделе [fenv_access](../../preprocessor/fenv-access.md).

## <a name="requirements"></a>Требования

|Функция|Заголовок C|Заголовок C++|
|--------------|--------------|------------------|
|**fegetenv**|\<fenv.h>|\<cfenv>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Алфавитный указатель функций](crt-alphabetical-function-reference.md)<br/>
[fesetenv](fesetenv1.md)<br/>
