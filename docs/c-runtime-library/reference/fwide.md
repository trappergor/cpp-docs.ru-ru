---
title: fwide
ms.date: 11/04/2016
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
helpviewer_keywords:
- fwide function
ms.assetid: a4641f5b-d74f-4946-95d5-53a64610d28d
ms.openlocfilehash: d992ebc527744beeb4ef14175e3f10646a77a064
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62287620"
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

*поток*<br/>
Указатель на **ФАЙЛ** структуры (игнорируются).

*mode*<br/>
Новая ширина потока: положительное значение для расширенных символов, отрицательное для байта, ноль, чтобы оставить без изменений. (Это значение игнорируется.)

## <a name="return-value"></a>Возвращаемое значение

Эта функция в настоящее время просто возвращает *режим*.

## <a name="remarks"></a>Примечания

Текущая версия этой функции не соответствует стандарту.

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|
|--------------|---------------------|
|**fwide**|\<wchar.h>|

Дополнительные сведения см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).