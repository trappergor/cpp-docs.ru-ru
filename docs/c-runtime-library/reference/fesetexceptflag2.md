---
title: fesetexceptflag | Документы Microsoft
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
apiname:
- fesetexceptflag
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
- fesetexceptflag
- fenv/fesetexceptflag
dev_langs:
- C++
helpviewer_keywords:
- fesetexceptflag function
ms.assetid: 2f7dad77-9e54-4097-a3e3-35176ace4de5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eef8ba1c91e6db4f0d620ef820a6487b3b17e649
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32398612"
---
# <a name="fesetexceptflag"></a>fesetexceptflag

Задает указанные флаги состояний с плавающей запятой в текущей среде вычислений с плавающей запятой.

## <a name="syntax"></a>Синтаксис

```C
int fesetexceptflag(
     const fexcept_t *pstatus,
     int excepts
);
```

### <a name="parameters"></a>Параметры

*pstatus*<br/>
Указатель на **fexcept_t** объект, содержащий значения присваивается исключение флагов состояния. Объект может задаваться в рамках предыдущего вызова функции [fegetexceptflag](fegetexceptflag2.md).

*excepts*<br/>
Флаги состояний исключения с плавающей запятой, которые требуется задать.

## <a name="return-value"></a>Возвращаемое значение

Если успешно заданы все указанные флаги состояний исключения, возвращает 0. В противном случае возвращается ненулевое значение.

## <a name="remarks"></a>Примечания

**Fesetexceptflag** функция задает состояние флагов состояния исключения с плавающей запятой, определяемое *excepts* для соответствующего значения, заданные в **fexcept_t** Объект, на который указывает *pstatus*.  При этом не вызывается исключение. *Pstatus* указатель должен указывать на допустимый **fexcept_t** объекта или последующее поведение не определено. **Fesetexceptflag** функция поддерживает эти значения макроса исключений в *excepts*, определенного в \<fenv.h >:

|Макрос исключения|Описание|
|---------------------|-----------------|
|FE_DIVBYZERO|При выполнении предыдущей операции с плавающей запятой произошла ошибка сингулярности или полюса, в результате чего было получено бесконечное значение.|
|FE_INEXACT|Функция принудительно округлила сохраненный результат ранее выполненной операции с плавающей запятой.|
|FE_INVALID|Ошибка домена в ранее выполненной операции с плавающей запятой.|
|FE_OVERFLOW|Ошибка диапазона. Ранее выполненная операция с плавающей запятой возвратила слишком большое значение, которое не удается представить.|
|FE_UNDERFLOW|Ранее выполненная операция с плавающей запятой возвратила слишком малое значение, которое не удается представить с полной точностью. Создано денормализованное значение.|
|FE_ALLEXCEPT|Побитовая операция ИЛИ для всех поддерживаемых исключений с плавающей запятой.|

*Excepts* аргумент может иметь ноль, один из макросов поддерживаемых исключений с плавающей запятой или побитового или двух или более макросов. Действие любого другого значения аргумента не определено.

Чтобы использовать эту функцию, необходимо отключить оптимизацию вычислений с плавающей запятой, которая может препятствовать доступу. Для этого следует использовать директиву `#pragma fenv_access(on)` перед вызовом. Дополнительные сведения см. в разделе [fenv_access](../../preprocessor/fenv-access.md).

## <a name="requirements"></a>Требования

|Функция|Заголовок C|Заголовок C++|
|--------------|--------------|------------------|
|**fesetexceptflag**|\<fenv.h>|\<cfenv>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Алфавитный указатель функций](crt-alphabetical-function-reference.md)<br/>
[fegetexceptflag](fegetexceptflag2.md)<br/>
