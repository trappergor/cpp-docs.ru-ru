---
title: feraiseexcept
ms.date: 04/05/2018
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
helpviewer_keywords:
- feraiseexcept function
ms.assetid: 87e89151-83c2-4563-9a9a-45666245d437
ms.openlocfilehash: 581dd4026a20ce7221945c5815af3ae102f132fa
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62334363"
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

*Кроме*<br/>
Исключения с плавающей запятой, которые необходимо вызвать.

## <a name="return-value"></a>Возвращаемое значение

Если все заданные исключения вызваны успешно, возвращается 0.

## <a name="remarks"></a>Примечания

**Feraiseexcept** функция пытается вызывать исключения с плавающей запятой, заданные *кроме*.   **Feraiseexcept** функция поддерживает макросы исключений, определенные в \<fenv.h >:

|Макрос исключения|Описание|
|---------------------|-----------------|
|FE_DIVBYZERO|При выполнении предыдущей операции с плавающей запятой произошла ошибка сингулярности или полюса, в результате чего было получено бесконечное значение.|
|FE_INEXACT|Функция принудительно округлила сохраненный результат ранее выполненной операции с плавающей запятой.|
|FE_INVALID|Ошибка домена в ранее выполненной операции с плавающей запятой.|
|FE_OVERFLOW|Ошибка диапазона. Ранее выполненная операция с плавающей запятой возвратила слишком большое значение, которое не удается представить.|
|FE_UNDERFLOW|Ранее выполненная операция с плавающей запятой возвратила слишком малое значение, которое не удается представить с полной точностью. Создано денормализованное значение.|
|FE_ALLEXCEPT|Побитовая операция ИЛИ для всех поддерживаемых исключений с плавающей запятой.|

*Кроме* аргумент может иметь ноль, один значения макросов исключений, а также побитовой операции или двух или более из поддерживаемого макроса исключения. Если один из указанных макросов исключений имеет значение FE_OVERFLOW или FE_UNDERFLOW, в качестве побочного эффекта может быть вызвано исключение FE_INEXACT.

Чтобы использовать эту функцию, необходимо отключить оптимизацию вычислений с плавающей запятой, которая может препятствовать доступу. Для этого следует использовать директиву `#pragma fenv_access(on)` перед вызовом. Дополнительные сведения см. в разделе [fenv_access](../../preprocessor/fenv-access.md).

**Систем Майкрософт:** Исключения, указанные в *кроме* вызываются в порядке FE_INVALID, FE_DIVBYZERO, FE_OVERFLOW, FE_UNDERFLOW, FE_INEXACT. Тем не менее, FE_INEXACT может вызываться при возникновении FE_OVERFLOW или FE_UNDERFLOW, даже если не указан в *кроме*. **Завершение блока, относящегося только к системам Майкрософт**

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
