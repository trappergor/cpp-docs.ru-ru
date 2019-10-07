---
title: isleadbyte, _isleadbyte_l
ms.date: 11/04/2016
api_name:
- _isleadbyte_l
- isleadbyte
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
- api-ms-win-crt-string-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _istleadbyte
- _isleadbyte_l
- isleadbyte
helpviewer_keywords:
- lead bytes
- _isleadbyte_l function
- _istleadbyte function
- istleadbyte function
- isleadbyte function
ms.assetid: 3b2bcf09-d82b-4803-9e80-59d04942802a
ms.openlocfilehash: 6b853dcea82c2afea91b2e0545d253786c88ae5e
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70954312"
---
# <a name="isleadbyte-_isleadbyte_l"></a>isleadbyte, _isleadbyte_l

Определяет, является ли символ начальным байтом многобайтового символа.

> [!IMPORTANT]
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
int isleadbyte( int c );
int _isleadbyte_l( int c );
```

### <a name="parameters"></a>Параметры

*c*<br/>
Проверяемое целое число.

## <a name="return-value"></a>Возвращаемое значение

**ислеадбите** возвращает ненулевое значение, если аргумент удовлетворяет условию теста, или 0, если нет. В языковых стандартах "C" и в национальных кодировках однобайтовых кодировок (SBCS) **ислеадбите** всегда возвращает 0.

## <a name="remarks"></a>Примечания

Макрос **ислеадбите** возвращает ненулевое значение, если его аргумент является первым байтом многобайтового символа. **ислеадбите** дает осмысленный результат для любого целочисленного аргумента от-1 (**EOF**) до **UCHAR_MAX** (0xFF) включительно.

Ожидаемый тип аргумента для **ислеадбите** — **int**; Если передается знак подписывания, компилятор может преобразовать его в целое число по расширению знака, что приведет к непредсказуемым результатам.

Версия этой функции с суффиксом **_l** идентична за исключением того, что использует переданный языковой стандарт вместо текущего языкового стандарта для поведения, зависящего от языкового стандарта.

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_istleadbyte**|Всегда возвращает значение false|**_isleadbyte**|Всегда возвращает значение false|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**isleadbyte**|\<ctype.h>|
|**_isleadbyte_l**|\<ctype.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Классификация байтов](../../c-runtime-library/byte-classification.md)<br/>
[Языковой стандарт](../../c-runtime-library/locale.md)<br/>
[Подпрограммы _ismbb](../../c-runtime-library/ismbb-routines.md)<br/>
