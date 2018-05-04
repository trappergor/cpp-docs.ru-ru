---
title: fwide | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- fwide
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
apitype: DLLExport
f1_keywords:
- fwide
dev_langs:
- C++
helpviewer_keywords:
- fwide function
ms.assetid: a4641f5b-d74f-4946-95d5-53a64610d28d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fd52c450e2eb34c40d44d00a76550c401abcb6c9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="fwide"></a>fwide

Не реализовано.

## <a name="syntax"></a>Синтаксис

```C
int fwide(
   FILE *stream,
   int mode;
);
```

### <a name="parameters"></a>Параметры

*Поток*<br/>
Указатель на **ФАЙЛ** структуры (пропускается).

*mode*<br/>
Новая ширина потока: положительное значение для расширенных символов, отрицательное для байта, ноль, чтобы оставить без изменений. (Это значение игнорируется.)

## <a name="return-value"></a>Возвращаемое значение

Эта функция в настоящее время только возвращает *режим*.

## <a name="remarks"></a>Примечания

Текущая версия этой функции не соответствует стандарту.

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|
|--------------|---------------------|
|**fwide**|\<wchar.h>|

Дополнительные сведения см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).