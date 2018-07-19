---
title: feraiseexcept | Документы Майкрософт
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
apiname:
- feraiseexcept
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
apitype: HeaderDef
f1_keywords:
- feraiseexcept
- fenv/feraiseexcept
dev_langs:
- C++
helpviewer_keywords:
- feraiseexcept function
ms.assetid: 87e89151-83c2-4563-9a9a-45666245d437
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dfd60612c92f8e3ff542fd22bbf5b4a01f7b7365
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32398641"
---
# <a name="feraiseexcept"></a>feraiseexcept

Вызывает указанные исключения с плавающей запятой.

## <a name="syntax"></a>Синтаксис

```C
int feraiseexcept(
   int excepts
);
```

### <a name="parameters"></a>Параметры

*excepts*<br/>
Исключения с плавающей запятой, которые необходимо вызвать.

## <a name="return-value"></a>Возвращаемое значение

Если все заданные исключения вызваны успешно, возвращается 0.

## <a name="remarks"></a>Примечания

**Feraiseexcept** функция пытается вызвать исключения с плавающей запятой, определяемое *excepts*.   **Feraiseexcept** функция поддерживает эти макросы исключений, определенных в \<fenv.h >:

|Макрос исключения|Описание|
|---------------------|-----------------|
|FE_DIVBYZERO|При выполнении предыдущей операции с плавающей запятой произошла ошибка сингулярности или полюса, в результате чего было получено бесконечное значение.|
|FE_INEXACT|Функция принудительно округлила сохраненный результат ранее выполненной операции с плавающей запятой.|
|FE_INVALID|Ошибка домена в ранее выполненной операции с плавающей запятой.|
|FE_OVERFLOW|Ошибка диапазона. Ранее выполненная операция с плавающей запятой возвратила слишком большое значение, которое не удается представить.|
|FE_UNDERFLOW|Ранее выполненная операция с плавающей запятой возвратила слишком малое значение, которое не удается представить с полной точностью. Создано денормализованное значение.|
|FE_ALLEXCEPT|Побитовая операция ИЛИ для всех поддерживаемых исключений с плавающей запятой.|

*Excepts* аргумент может иметь ноль, один из значения макроса исключений или побитовое или двух или более макросов исключение поддерживается. Если один из указанных макросов исключений имеет значение FE_OVERFLOW или FE_UNDERFLOW, в качестве побочного эффекта может быть вызвано исключение FE_INEXACT.

Чтобы использовать эту функцию, необходимо отключить оптимизацию вычислений с плавающей запятой, которая может препятствовать доступу. Для этого следует использовать директиву `#pragma fenv_access(on)` перед вызовом. Дополнительные сведения см. в разделе [fenv_access](../../preprocessor/fenv-access.md).

**К системам Microsoft:** исключения, указанный в *excepts* вызываются в порядке FE_INVALID, FE_DIVBYZERO, FE_OVERFLOW, FE_UNDERFLOW, FE_INEXACT. Тем не менее, FE_INEXACT может возникнуть, когда происходит событие FE_OVERFLOW или FE_UNDERFLOW, даже если не указан в *excepts*. **Завершение блока, относящегося только к системам Майкрософт**

## <a name="requirements"></a>Требования

|Функция|Заголовок C|Заголовок C++|
|--------------|--------------|------------------|
|*feraiseexcept*|\<fenv.h>|\<cfenv>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Алфавитный указатель функций](crt-alphabetical-function-reference.md)<br/>
[fesetexceptflag](fesetexceptflag2.md)<br/>
[feholdexcept](feholdexcept2.md)<br/>
[fetestexcept](fetestexcept1.md)<br/>
[feupdateenv](feupdateenv.md)<br/>
