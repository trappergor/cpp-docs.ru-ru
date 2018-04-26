---
title: _get_FMA3_enable _set_FMA3_enable | Документы Microsoft
ms.custom: ''
ms.date: 04/05/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- _get_FMA3_enable
- _set_FMA3_enable
ms.assetid: 4c1dc4bc-e86b-451b-9211-5a2ba6c98ee4
caps.latest.revision: 1
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 84087e0883aef3de65081dd2337b8ec588bd1528
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2018
---
# <a name="getfma3enable-setfma3enable"></a>_get_FMA3_enable _set_FMA3_enable

Возвращает или задает флаг, указывающий, использовать ли трансцендентной математические функции с плавающей запятой библиотеки FMA3 инструкции в коде, скомпилированном для X64 платформы.

## <a name="syntax"></a>Синтаксис

```C
int _set_FMA3_enable(int flag);
int _get_FMA3_enable();
```

### <a name="parameters"></a>Параметры

*Флаг*<br/>
Значение 1, чтобы включить реализаций FMA3 трансцендентной математические функции с плавающей запятой библиотеки на X64 платформы, или 0, чтобы использовать реализации, не использующих FMA3 инструкции.

## <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если включены FMA3 реализации функций трансцендентной математической библиотеки с плавающей запятой. В противном случае возвращается ноль.

## <a name="remarks"></a>Примечания

Используйте **_set_FMA3_enable** функции, чтобы включить или отключить использование FMA3 инструкциям трансцендентной математические функции с плавающей запятой в библиотеки CRT. Возвращаемое значение отражает реализация используется после изменения. Если Процессор не поддерживает инструкции FMA3, эта функция не может включить ее в библиотеке, и возвращаемое значение равно нулю. Используйте **_get_FMA3_enable** для получения текущего состояния библиотеки. По умолчанию на X64 платформы, код запуска CRT обнаруживает ли ЦП поддерживает FMA3 инструкции и включает или отключает реализации FMA3 в библиотеке.

Реализации FMA3 используют разные алгоритмы, небольшие различия в результатах вычисления возможно наблюдаемый объект при реализации FMA3 включены или отключены или между компьютерами, которые или не поддерживают FMA3. Дополнительные сведения см. в разделе [проблемы при миграции с плавающей запятой](../../porting/floating-point-migration-issues.md).

## <a name="requirements"></a>Требования

**_Set_FMA3_enable** и **_get_FMA3_enable** функции доступны только в X64 версии библиотек CRT.

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_set_FMA3_enable**, **_get_FMA3_enable**| C: \<math.h><br />C++: \<cmath > или \<math.h >|

**_Set_FMA3_enable** и **_get_FMA3_enable** функции — только к системам Майкрософт. Сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Поддержка плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[Проблемы при миграции с плавающей запятой](../../porting/floating-point-migration-issues.md)<br/>
