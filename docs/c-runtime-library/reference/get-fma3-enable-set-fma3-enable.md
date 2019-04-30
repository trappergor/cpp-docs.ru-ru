---
title: _get_FMA3_enable, _set_FMA3_enable
ms.date: 04/05/2018
apiname:
- _get_FMA3_enable
- _set_FMA3_enable
apilocation:
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _get_FMA3_enable
- _set_FMA3_enable
- math/_get_FMA3_enable
- math/_set_FMA3_enable
helpviewer_keywords:
- _get_FMA3_enable
- _set_FMA3_enable
ms.assetid: 4c1dc4bc-e86b-451b-9211-5a2ba6c98ee4
ms.openlocfilehash: 19eabc3b5a11246d5b0056bdafbb169e2a7de9f2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62332199"
---
# <a name="getfma3enable-setfma3enable"></a>_get_FMA3_enable, _set_FMA3_enable

Получает или задает флаг, указывающий, использовать ли функций трансцендентное математической библиотеки с плавающей запятой инструкций FMA3 в коде, скомпилированном для X64 платформ.

## <a name="syntax"></a>Синтаксис

```C
int _set_FMA3_enable(int flag);
int _get_FMA3_enable();
```

### <a name="parameters"></a>Параметры

*Флаг*<br/>
Значение 1 включает FMA3 реализации функций трансцендентное математической библиотеки с плавающей запятой в X64 платформ, или 0, чтобы использовать реализации, которые не используют FMA3 инструкции.

## <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если включены FMA3 реализации функций трансцендентное математической библиотеки с плавающей запятой. В противном случае — нуль.

## <a name="remarks"></a>Примечания

Используйте **_set_FMA3_enable** функции, чтобы включить или отключить использование инструкций fma3 в трансцендентное математические функции с плавающей запятой в библиотеки CRT. Возвращаемое значение отражает реализации используется после изменения. Если Процессор не поддерживает инструкции FMA3, эта функция не может включить ее в библиотеке и возвращаемое значение равно нулю. Используйте **_get_FMA3_enable** для получения текущего состояния библиотеки. По умолчанию в X64 платформ, в коде запуска CRT обнаруживает ли ЦП поддерживает FMA3 инструкции и включает или отключает реализаций FMA3 в библиотеке.

Так как в реализациях FMA3 используют разные алгоритмы, небольшие различия в результатах вычислений может быть наблюдаемый объект при реализации FMA3 включены или отключены, или между компьютерами, которые не поддерживают FMA3 или. Дополнительные сведения см. в разделе [проблемы при миграции с плавающей запятой](../../porting/floating-point-migration-issues.md).

## <a name="requirements"></a>Требования

**_Set_FMA3_enable** и **_get_FMA3_enable** X64 доступны только функции версии библиотек CRT.

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_set_FMA3_enable**, **_get_FMA3_enable**| C: \<math.h><br />C++: \<cmath > или \<math.h >|

**_Set_FMA3_enable** и **_get_FMA3_enable** функции только к системам Майкрософт. Сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Поддержка плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[Проблемы при миграции с плавающей запятой](../../porting/floating-point-migration-issues.md)<br/>
