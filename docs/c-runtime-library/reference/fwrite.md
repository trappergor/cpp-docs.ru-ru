---
title: fwrite
ms.date: 4/2/2020
api_name:
- fwrite
- _o_fwrite
api_location:
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
- api-ms-win-crt-stdio-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- fwrite
helpviewer_keywords:
- streams, writing data to
- fwrite function
ms.assetid: 7afacf3a-72d7-4a50-ba2e-bea1ab9f4124
ms.openlocfilehash: a5bd6da3c8d16189f7ff0db744901e03513acc21
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81345397"
---
# <a name="fwrite"></a>fwrite

Записывает данные в поток.

## <a name="syntax"></a>Синтаксис

```C
size_t fwrite(
   const void *buffer,
   size_t size,
   size_t count,
   FILE *stream
);
```

### <a name="parameters"></a>Параметры

*Буфера*<br/>
Указатель на записываемые данные.

*Размер*<br/>
Размер элемента, в байтах.

*count*<br/>
Максимальное число записываемых элементов.

*Поток*<br/>
Указатель на структуру **FILE**.

## <a name="return-value"></a>Возвращаемое значение

**fwrite** возвращает количество фактически написанных полных элементов, что может быть меньше, чем *количество,* если ошибка происходит. Кроме того, в случае возникновения ошибки невозможно определить индикатор положения файла. Если *поток* или *буфер* является нулевой указателем, или если в режиме Unicode указывается нечетное число байтов, функция вызывает обработчик параметров, как описано в [проверке параметра.](../../c-runtime-library/parameter-validation.md) Если выполнение разрешено продолжать, эта функция устанавливает **errno** к **EINVAL** и возвращает 0.

## <a name="remarks"></a>Remarks

Функция **fwrite** записывает для *подсчета* элементов, *длины размера* каждого, от *буфера* до выходного *потока.* Указатель файла, связанный с *потоком* (если он есть) приращена числом фактически написанных байтов. Если *поток* открыт в текстовом режиме, каждая линия корма заменяется парой корма возврата каретной линии. Замена не влияет на возвращаемое значение.

Когда *поток* открыт в режиме перевода Unicode, например, если *поток* открывается путем вызова **fopen** и использования параметра режима, который включает в себя **ccs-UNICODE,** **ccs-UTF-16LE**, или **ccs'UTF-8**, или если режим изменен **wchar_t** на режим Unicode перевод с помощью **_setmode** и параметра режима, который включает в себя **_O_WTEXT,** **_O_U16TEXT,** или **_O_U8TEXT**-*буфер* интерпретируется как указатель на wchar_t. Попытка записи нечетного числа байт в этом режиме приводит к возникновению ошибки проверки параметра.

Поскольку эта функция блокирует вызывающий поток, она потокобезопасна. Для неблокирующей версии **_fwrite_nolock**см.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Компонент|Обязательный заголовок|
|--------------|---------------------|
|**fwrite**|\<stdio.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

См. пример для [fread](fread.md).

## <a name="see-also"></a>См. также раздел

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[_setmode](setmode.md)<br/>
[fread](fread.md)<br/>
[_fwrite_nolock](fwrite-nolock.md)<br/>
[_write](write.md)<br/>
