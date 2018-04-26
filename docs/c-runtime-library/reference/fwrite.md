---
title: fwrite | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- fwrite
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- fwrite
dev_langs:
- C++
helpviewer_keywords:
- streams, writing data to
- fwrite function
ms.assetid: 7afacf3a-72d7-4a50-ba2e-bea1ab9f4124
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3b91ad6efe0573bc469e0752ed27978b12018ee7
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2018
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

*buffer*<br/>
Указатель на записываемые данные.

*size*<br/>
Размер элемента, в байтах.

*count*<br/>
Максимальное число записываемых элементов.

*Поток*<br/>
Указатель на структуру **FILE**.

## <a name="return-value"></a>Возвращаемое значение

**fwrite** возвращает число полных фактически записанных элементов, которое может быть меньше, чем *число* при возникновении ошибки. Кроме того, в случае возникновения ошибки невозможно определить индикатор положения файла. Если параметр *поток* или *буфера* является пустым указателем, или если указано нечетное число байтов для записи в режиме Юникода, функция вызывает обработчик недопустимого параметра, как описано в [ Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эта функция задает **errno** для **EINVAL** и возвращает 0.

## <a name="remarks"></a>Примечания

**Fwrite** функция записывает до *число* элементы, из *размер* каждый длиной от *буфера* к выходу *поток*. Указатель файла, связанного с *поток* (если есть) увеличивается на число фактически записанных байт. Если *поток* открыт в текстовом режиме, каждый перевод строки заменяется возврат каретки — перевод строки пары. Замена не влияет на возвращаемое значение.

При *поток* открывается в режиме преобразования Юникода — например, если *поток* открывается вызовом **fopen** и с помощью параметра режима, который включает **ccs = ЮНИКОДА**, **ccs = UTF-16LE**, или **ccs = UTF-8**, или если режим изменяется на режим преобразования Юникода с помощью **_setmode** и режим параметр, который включает в себя **_O_WTEXT**, **_O_U16TEXT**, или **_O_U8TEXT**—*буфера* интерпретируется как указатель на Массив **wchar_t** , содержащий данные UTF-16. Попытка записи нечетного числа байт в этом режиме приводит к возникновению ошибки проверки параметра.

Поскольку эта функция блокирует вызывающий поток, она потокобезопасна. Неблокирующей версии см. **_fwrite_nolock**.

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|
|--------------|---------------------|
|**fwrite**|\<stdio.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

См. пример для [fread](fread.md).

## <a name="see-also"></a>См. также

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[_setmode](setmode.md)<br/>
[fread](fread.md)<br/>
[_fwrite_nolock](fwrite-nolock.md)<br/>
[_write](write.md)<br/>
