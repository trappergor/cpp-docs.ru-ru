---
title: Справочник по кодировке ATL
ms.date: 11/04/2016
helpviewer_keywords:
- encoding
- encoding, functions
ms.assetid: 82d4fdf3-3c4a-4fe2-b297-8ffb4714406f
ms.openlocfilehash: a9c7689e49efce0d65e945f1a032a680e2277594
ms.sourcegitcommit: 878a164fe6d550ca81ab87d8425c8d3cd52fe384
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/22/2019
ms.locfileid: "68375866"
---
# <a name="atl-encoding-reference"></a>Справочник по кодировке ATL

Кодирование в диапазоне распространенных стандартов Интернета, таких как uuencode, шестнадцатеричные и UTF8, поддерживается кодом, найденным в файла atlenc. h.

### <a name="functions"></a>Функции

|||
|-|-|
|[атлжесексвалуе](reference/atl-text-encoding-functions.md#atlgethexvalue)|Вызывайте эту функцию для получения числового значения шестнадцатеричной цифры.|
|[атлхексдекоде](reference/atl-text-encoding-functions.md#atlhexdecode)|Декодирует строку данных, закодированную как шестнадцатеричный текст, например, с помощью предыдущего вызова [атлхексенкоде](reference/atl-text-encoding-functions.md#atlhexencode).|
|[атлхексдекодежетрекуиредленгс](reference/atl-text-encoding-functions.md#atlhexdecodegetrequiredlength)|Вызывайте эту функцию для получения размера (в байтах) буфера, который может содержать декодированные данные из шестнадцатеричной кодированной строки указанной длины.|
|[атлхексенкоде](reference/atl-text-encoding-functions.md#atlhexencode)|Вызывайте эту функции для кодирования некоторых данных в виде строки шестнадцатеричного текста.|
|[атлхексенкодежетрекуиредленгс](reference/atl-text-encoding-functions.md#atlhexencodegetrequiredlength)|Вызывайте эту функцию для получения размера (в символах) буфера, который может содержать строку, закодированную из данных указанного размера.|
|[AtlUnicodeToUTF8](reference/atl-text-encoding-functions.md#atlunicodetoutf8)|Вызывайте эту функцию для преобразования строки Юникода в UTF-8.|
|[бенкоде](reference/atl-text-encoding-functions.md#bencode)|Вызывайте эту функцию для преобразования некоторых данных с использованием кодировки "B".|
|[бенкодежетрекуиредленгс](reference/atl-text-encoding-functions.md#bencodegetrequiredlength)|Вызывайте эту функцию для получения размера (в символах) буфера, который может содержать строку, закодированную из данных указанного размера.|
|[EscapeXML](reference/atl-text-encoding-functions.md#escapexml)|Вызывайте эту функцию для преобразования символов, небезопасных для использования в XML, в их безопасные эквиваленты.|
|[жетекстендедчарс](reference/atl-text-encoding-functions.md#getextendedchars)|Вызывайте эту функцию для получения количества символов национального алфавита в строке.|
|[исекстендедчар](reference/atl-text-encoding-functions.md#isextendedchar)|Вызывайте эту функцию, чтобы определить, является ли заданный символ расширенным символом (меньше 32, больше 126, а не символами табуляции, перевода строки или возврата каретки).|
|[кенкоде](reference/atl-text-encoding-functions.md#qencode)|Вызывайте эту функцию для преобразования некоторых данных с использованием кодировки "Q".|
|[кенкодежетрекуиредленгс](reference/atl-text-encoding-functions.md#qencodegetrequiredlength)|Вызывайте эту функцию для получения размера (в символах) буфера, который может содержать строку, закодированную из данных указанного размера.|
|[кпдекоде](reference/atl-text-encoding-functions.md#qpdecode)|Декодирует строку данных, закодированную в формате, заключенном в кавычки, например, с помощью предыдущего вызова [кпенкоде](reference/atl-text-encoding-functions.md#qpencode).|
|[кпдекодежетрекуиредленгс](reference/atl-text-encoding-functions.md#qpdecodegetrequiredlength)|Вызывайте эту функцию для получения размера (в байтах) буфера, который может содержать декодированные данные из строки указанной длины, закодированной в печатаемом формате с кавычками (quoted-printable).|
|[кпенкоде](reference/atl-text-encoding-functions.md#qpencode)|Вызывайте эту функцию для кодирования некоторых данных в печатаемом формате с кавычками (quoted-printable).|
|[кпенкодежетрекуиредленгс](reference/atl-text-encoding-functions.md#qpencodegetrequiredlength)|Вызывайте эту функцию для получения размера (в символах) буфера, который может содержать строку, закодированную из данных указанного размера.|
|[уудекоде](reference/atl-text-encoding-functions.md#uudecode)|Декодирует строку данных, которая была ууенкодед, например, с помощью предыдущего вызова [uuencode](reference/atl-text-encoding-functions.md#uuencode).|
|[уудекодежетрекуиредленгс](reference/atl-text-encoding-functions.md#uudecodegetrequiredlength)|Вызывайте эту функцию для получения размера (в байтах) буфера, который может содержать декодированные данные из строки указанной длины в кодировке UUEncode.|
|[UUEncode](reference/atl-text-encoding-functions.md#uuencode)|Вызывайте эту функцию для кодирования данных в кодировке UUEncode.|
|[ууенкодежетрекуиредленгс](reference/atl-text-encoding-functions.md#uuencodegetrequiredlength)|Вызывайте эту функцию для получения размера (в символах) буфера, который может содержать строку, закодированную из данных указанного размера.|

## <a name="see-also"></a>См. также

[Основные понятия](../atl/active-template-library-atl-concepts.md)<br/>
[Компоненты ATL COM Desktop](../atl/atl-com-desktop-components.md)
