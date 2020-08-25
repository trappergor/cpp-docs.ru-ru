---
title: Справочник по кодировке ATL
ms.date: 11/04/2016
helpviewer_keywords:
- encoding
- encoding, functions
ms.assetid: 82d4fdf3-3c4a-4fe2-b297-8ffb4714406f
ms.openlocfilehash: a284645030b5bcdb30b72d7df92231680efb36b4
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88831896"
---
# <a name="atl-encoding-reference"></a>Справочник по кодировке ATL

Кодирование в диапазоне распространенных стандартов Интернета, таких как uuencode, шестнадцатеричные и UTF8, поддерживается кодом, найденным в *`atlenc.h`* .

### <a name="functions"></a>Функции

| Компонент | Вариант использования |
|--|--|
| [AtlGetHexValue](reference/atl-text-encoding-functions.md#atlgethexvalue) | Вызывайте эту функцию для получения числового значения шестнадцатеричной цифры. |
| [AtlHexDecode](reference/atl-text-encoding-functions.md#atlhexdecode) | Декодирует строку данных, закодированную как шестнадцатеричный текст, например, с помощью предыдущего вызова [атлхексенкоде](reference/atl-text-encoding-functions.md#atlhexencode). |
| [AtlHexDecodeGetRequiredLength](reference/atl-text-encoding-functions.md#atlhexdecodegetrequiredlength) | Вызывайте эту функцию для получения размера (в байтах) буфера, который может содержать декодированные данные из шестнадцатеричной кодированной строки указанной длины. |
| [AtlHexEncode](reference/atl-text-encoding-functions.md#atlhexencode) | Вызывайте эту функции для кодирования некоторых данных в виде строки шестнадцатеричного текста. |
| [AtlHexEncodeGetRequiredLength](reference/atl-text-encoding-functions.md#atlhexencodegetrequiredlength) | Вызывайте эту функцию для получения размера (в символах) буфера, который может содержать строку, закодированную из данных указанного размера. |
| [AtlUnicodeToUTF8](reference/atl-text-encoding-functions.md#atlunicodetoutf8) | Вызывайте эту функцию для преобразования строки Юникода в UTF-8. |
| [BEncode](reference/atl-text-encoding-functions.md#bencode) | Вызывайте эту функцию для преобразования некоторых данных с использованием кодировки "B". |
| [BEncodeGetRequiredLength](reference/atl-text-encoding-functions.md#bencodegetrequiredlength) | Вызывайте эту функцию для получения размера (в символах) буфера, который может содержать строку, закодированную из данных указанного размера. |
| [EscapeXML](reference/atl-text-encoding-functions.md#escapexml) | Вызывайте эту функцию для преобразования символов, небезопасных для использования в XML, в их безопасные эквиваленты. |
| [GetExtendedChars](reference/atl-text-encoding-functions.md#getextendedchars) | Вызывайте эту функцию для получения количества символов национального алфавита в строке. |
| [IsExtendedChar](reference/atl-text-encoding-functions.md#isextendedchar) | Вызывайте эту функцию, чтобы определить, является ли заданный символ расширенным символом (меньше 32, больше 126, а не символами табуляции, перевода строки или возврата каретки). |
| [QEncode](reference/atl-text-encoding-functions.md#qencode) | Вызывайте эту функцию для преобразования некоторых данных с использованием кодировки "Q". |
| [QEncodeGetRequiredLength](reference/atl-text-encoding-functions.md#qencodegetrequiredlength) | Вызывайте эту функцию для получения размера (в символах) буфера, который может содержать строку, закодированную из данных указанного размера. |
| [QPDecode](reference/atl-text-encoding-functions.md#qpdecode) | Декодирует строку данных, закодированную в формате, заключенном в кавычки, например, с помощью предыдущего вызова [кпенкоде](reference/atl-text-encoding-functions.md#qpencode). |
| [QPDecodeGetRequiredLength](reference/atl-text-encoding-functions.md#qpdecodegetrequiredlength) | Вызывайте эту функцию для получения размера (в байтах) буфера, который может содержать декодированные данные из строки указанной длины, закодированной в печатаемом формате с кавычками (quoted-printable). |
| [QPEncode](reference/atl-text-encoding-functions.md#qpencode) | Вызывайте эту функцию для кодирования некоторых данных в печатаемом формате с кавычками (quoted-printable). |
| [QPEncodeGetRequiredLength](reference/atl-text-encoding-functions.md#qpencodegetrequiredlength) | Вызывайте эту функцию для получения размера (в символах) буфера, который может содержать строку, закодированную из данных указанного размера. |
| [UUDecode](reference/atl-text-encoding-functions.md#uudecode) | Декодирует строку данных, которая была ууенкодед, например, с помощью предыдущего вызова [uuencode](reference/atl-text-encoding-functions.md#uuencode). |
| [UUDecodeGetRequiredLength](reference/atl-text-encoding-functions.md#uudecodegetrequiredlength) | Вызывайте эту функцию для получения размера (в байтах) буфера, который может содержать декодированные данные из строки указанной длины в кодировке UUEncode. |
| [UUEncode](reference/atl-text-encoding-functions.md#uuencode) | Вызывайте эту функцию для кодирования данных в кодировке UUEncode. |
| [UUEncodeGetRequiredLength](reference/atl-text-encoding-functions.md#uuencodegetrequiredlength) | Вызывайте эту функцию для получения размера (в символах) буфера, который может содержать строку, закодированную из данных указанного размера. |

## <a name="see-also"></a>См. также раздел

[Концепции](../atl/active-template-library-atl-concepts.md)<br/>
[Компоненты ATL COM Desktop](../atl/atl-com-desktop-components.md)
