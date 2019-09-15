---
title: _cgets_s, _cgetws_s
ms.date: 11/04/2016
api_name:
- _cgetws_s
- _cgets_s
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
- api-ms-win-crt-conio-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _cgets_s
- cgets_s
- cgetws_s
- _cgetws_s
helpviewer_keywords:
- strings [C++], getting from console
- console, getting strings from
- _cgets_s function
- cget_s function
- _cgetws_s function
- cgetws_s function
ms.assetid: 38b74897-afe6-4dd9-a43f-36a3c0d72c5c
ms.openlocfilehash: 2039fc32cecb768c3c3fbc239446abedeb48f188
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70939266"
---
# <a name="_cgets_s-_cgetws_s"></a>_cgets_s, _cgetws_s

Возвращает строку символов из консоли. Это версии функций [_cgets и _cgetws](../../c-runtime-library/cgets-cgetws.md) с усовершенствованной безопасностью, как описано в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

> [!IMPORTANT]
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
errno_t _cgets_s(
   char *buffer,
   size_t numberOfElements,
   size_t *pSizeRead
);
errno_t _cgetws_s(
   wchar_t *buffer
   size_t numberOfElements,
   size_t *pSizeRead
);
template <size_t size>
errno_t _cgets_s(
   char (&buffer)[size],
   size_t *pSizeRead
); // C++ only
template <size_t size>
errno_t _cgetws_s(
   wchar_t (&buffer)[size],
   size_t *pSizeRead
); // C++ only
```

### <a name="parameters"></a>Параметры

*buffer*<br/>
Место хранения данных.

*numberOfElements*<br/>
Размер буфера в однобайтовых или расширенных символах, который также представляет максимальное число символов для чтения.

*псизереад*<br/>
Число фактически прочитанных символов.

## <a name="return-value"></a>Возвращаемое значение

При успешном выполнении возвращается ноль, в противном случае возвращается код ошибки.

### <a name="error-conditions"></a>Условия ошибок

|*buffer*|*numberOfElements*|*псизереад*|Назад|Содержимое *буфера*|
|--------------|------------------------|-----------------|------------|--------------------------|
|**NULL**|Любое действие|Любое действие|**EINVAL**|Н/Д|
|не **null**|нуль|Любое действие|**EINVAL**|не изменено|
|не **null**|Любое действие|**NULL**|**EINVAL**|строка нулевой длины|

## <a name="remarks"></a>Примечания

**_cgets_s** и **_cgetws_s** считывают строку из консоли и копируют строку (с нулевым символом конца) в *буфер*. **_cgetws_s** — это версия функции с расширенными символами; в отличие от размера символов, поведение этих двух функций идентично. Максимальный размер строки для чтения передается в качестве параметра *numberOfElements* . Размер должен учитывать дополнительный символ для конечного нуля. Фактическое число считанных символов помещается в *псизереад*.

Если во время операции или при проверке параметров возникает ошибка, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено **, возвращается** значение **Еинвал** , а **еинвал** возвращает.

В C++ использование данных функций упрощено наличием шаблонных перегрузок; перегруженные функции могут автоматически определять длину буфера (что исключает необходимость указания аргумента с размером буфера), а также они могут автоматически заменять более старые, незащищенные функции их новыми безопасными аналогами. Дополнительные сведения см. в разделе [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Процедура Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_cgetts_s**|**_cgets_s**|**_cgets_s**|**_cgetws_s**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_cgets_s**|\<conio.h>|
|**_cgetws_s**|\<conio.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Ввод-вывод на консоль и порт](../../c-runtime-library/console-and-port-i-o.md)<br/>
[_getch, _getwch](getch-getwch.md)<br/>
