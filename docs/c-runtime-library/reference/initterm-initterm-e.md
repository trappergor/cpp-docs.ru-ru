---
title: _initterm, _initterm_e | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _initterm_e
- _initterm
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
- _initterm_e
- initterm
- _initterm
- initterm_e
dev_langs:
- C++
helpviewer_keywords:
- initterm function
- initterm_e function
- _initterm function
- _initterm_e function
ms.assetid: 85131efe-c747-429a-8897-bcdedb000172
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 470ad6cbf13efb170f61aa12f7859f2baa248c2b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32395839"
---
# <a name="initterm-initterme"></a>_initterm, _initterm_e

Внутренние методы, которые выполняют обход таблицы указателей функций и инициализируют их.

Первый указатель представляет собой начальное расположение в таблице, а второй указатель — конечное расположение.

## <a name="syntax"></a>Синтаксис

```C
void __cdecl _initterm(
   PVFV *,
   PVFV *
);

int __cdecl _initterm_e(
   PVFV *,
   PVFV *
);
```

## <a name="return-value"></a>Возвращаемое значение

Ненулевой код ошибки, если инициализация завершается неудачей и генерирует ошибку; 0 при отсутствии ошибок.

## <a name="remarks"></a>Примечания

Эти методы вызываются только внутри системы во время инициализации программы C++. Не следует вызывать эти методы в программе.

Если эти методы производят обход таблицы записей функций, они пропускают **NULL** записей и продолжить.

## <a name="see-also"></a>См. также

[Алфавитный указатель функций](crt-alphabetical-function-reference.md)<br/>
