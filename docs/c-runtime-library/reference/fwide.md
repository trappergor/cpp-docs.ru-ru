---
title: fwide | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
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
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a055df312215b5ff424aff54cfee54e0568ab307
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2018
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