---
title: towctrans
ms.date: 11/04/2016
apiname:
- towctrans
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- towctrans
helpviewer_keywords:
- towctrans function
ms.assetid: 1ed1e70d-7b31-490f-a7d9-42564b5924ca
ms.openlocfilehash: b814c65d2f5d0bb18b19d97a539d79dd6df8a1c6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50561412"
---
# <a name="towctrans"></a>towctrans

Преобразует символ.

## <a name="syntax"></a>Синтаксис

```C
wint_t towctrans(
   wint_t c,
   wctrans_t category
);
```

### <a name="parameters"></a>Параметры

*c*<br/>
Символ, который требуется преобразовать.

*category*<br/>
Идентификатор, который содержит возвращаемое значение [wctrans](wctrans.md).

## <a name="return-value"></a>Возвращаемое значение

Символ *c*после **towctrans** использовала правило преобразования в *категории*.

## <a name="remarks"></a>Примечания

Значение *категории* должен быть возвращен с предыдущим успешным вызовом к [wctrans](wctrans.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**towctrans**|\<wctype.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

См. в разделе **wctrans** пример, использующий **towctrans**.

## <a name="see-also"></a>См. также

[Преобразование данных](../../c-runtime-library/data-conversion.md)<br/>
