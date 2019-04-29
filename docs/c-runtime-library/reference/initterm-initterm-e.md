---
title: _initterm, _initterm_e
ms.date: 11/04/2016
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
helpviewer_keywords:
- initterm function
- initterm_e function
- _initterm function
- _initterm_e function
ms.assetid: 85131efe-c747-429a-8897-bcdedb000172
ms.openlocfilehash: 65963e95507d4d6444ebcc9038b5b8cf797f9feb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62331666"
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

Когда эти методы производят обход таблицы записей функций, они пропускают **NULL** записи и продолжить.

## <a name="see-also"></a>См. также

[Алфавитный указатель функций](crt-alphabetical-function-reference.md)<br/>
