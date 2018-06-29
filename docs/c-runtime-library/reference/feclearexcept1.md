---
title: feclearexcept1 | Документы Майкрософт
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
apiname:
- feclearexcept
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
- feclearexcept
- fenv/feclearexcept
dev_langs:
- C++
helpviewer_keywords:
- feclearexcept function
ms.assetid: ef419da3-c248-4432-b53c-8e7a475d9533
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: face2637f308a56d95baa7563a6409dd38870d73
ms.sourcegitcommit: 2f571220e16f6c20e1fdb005f6cbc9e7ef5608f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/28/2018
ms.locfileid: "37070081"
---
# <a name="feclearexcept"></a>feclearexcept

Предпринимает попытку очистить флаги исключений с плавающей запятой, указанные в аргументе.

## <a name="syntax"></a>Синтаксис

```C
int feclearexcept(
   int excepts
);
```

### <a name="parameters"></a>Параметры

*excepts*<br/>
Флаги состояния исключения для очистки.

## <a name="return-value"></a>Возвращаемое значение

Возвращает нуль, если *excepts* равен нулю, или если все заданные исключения были успешно очищены. В противном случае возвращается ненулевое значение.

## <a name="remarks"></a>Примечания

**Feclearexcept** функция пытается очистить значение с плавающей точку флаги состояния исключения, определяемое *excepts*. Эта функция поддерживает макросы исключений, определенные в fenv.h:

|Макрос исключения|Описание:|
|---------------------|-----------------|
|FE_DIVBYZERO|При выполнении предыдущей операции с плавающей запятой произошла ошибка сингулярности или полюса, в результате чего было получено бесконечное значение.|
|FE_INEXACT|Функция принудительно округлила сохраненный результат ранее выполненной операции с плавающей запятой.|
|FE_INVALID|Ошибка домена в ранее выполненной операции с плавающей запятой.|
|FE_OVERFLOW|Ошибка диапазона. Ранее выполненная операция с плавающей запятой возвратила слишком большое значение, которое не удается представить.|
|FE_UNDERFLOW|Ранее выполненная операция с плавающей запятой возвратила слишком малое значение, которое не удается представить с полной точностью. Создано денормализованное значение.|
|FE_ALL_EXCEPT|Побитовая операция ИЛИ для всех поддерживаемых исключений с плавающей запятой.|

*Excepts* аргумент может иметь ноль или побитовое или из одного или нескольких макросов исключение поддерживается. Результат применения всех остальных значений аргумента не определен.

## <a name="requirements"></a>Требования

|Функция|Заголовок C|Заголовок C++|
|--------------|--------------|------------------|
|**feclearexcept**|\<fenv.h>|\<cfenv>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Алфавитный указатель функций](crt-alphabetical-function-reference.md)<br/>
[fetestexcept](fetestexcept1.md)<br/>
