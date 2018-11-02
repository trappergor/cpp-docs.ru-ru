---
title: isleadbyte, _isleadbyte_l
ms.date: 11/04/2016
apiname:
- _isleadbyte_l
- isleadbyte
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
ms.openlocfilehash: 1a3f427e49e53bb553020da100b0e713350fab3f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50531893"
---
# <a name="isleadbyte-isleadbytel"></a>isleadbyte, _isleadbyte_l

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

**isleadbyte** возвращает ненулевое значение, если аргумент удовлетворяет условию теста, или 0, если это не так. В языковом стандарте «C» и в однобайтовой кодировки (SBCS) национальных настроек, **isleadbyte** всегда возвращает значение 0.

## <a name="remarks"></a>Примечания

**Isleadbyte** макрос возвращает ненулевое значение, если его аргумент является первым байтом многобайтового символа. **isleadbyte** выдает значимый результат для любого целочисленного аргумента от – 1 (**EOF**) для **UCHAR_MAX** (0xFF) включительно.

Ожидаемый тип аргумента **isleadbyte** — **int**; Если передается символ со знаком, компилятор может преобразовать его в целое число по расширению знака, создавая непредсказуемые результаты.

Версия этой функции с **_l** суффиксом идентичны, за исключением того, что она использует переданный параметр языкового стандарта вместо текущего языкового стандарта для его поведения, зависящего от языкового стандарта.

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
