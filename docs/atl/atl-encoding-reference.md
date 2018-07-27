---
title: Справочник по кодировке ATL | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- encoding
- encoding, functions
ms.assetid: 82d4fdf3-3c4a-4fe2-b297-8ffb4714406f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1d8cbb23c390a47b1bbfb7b1a78b327f07b06869
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32358632"
---
# <a name="atl-encoding-reference"></a>Справочник по кодировке ATL
Кодирование в UTF8 и широкий набор общих стандартов Интернета как uuencode, шестнадцатеричный, поддерживается код содержится в файла atlenc.h.  
  
### <a name="functions"></a>Функции  
  
|||  
|-|-|  
|[AtlGetHexValue](reference/atl-text-encoding-functions.md#atlgethexvalue)|Вызывайте эту функцию для получения числового значения шестнадцатеричной цифры.|  
|[AtlHexDecode](reference/atl-text-encoding-functions.md#atlhexdecode)|Декодирует строку данных, которая была закодирована как шестнадцатеричный текст, например предыдущим вызовом [AtlHexEncode](reference/atl-text-encoding-functions.md#atlhexencode).|  
|[AtlHexDecodeGetRequiredLength](reference/atl-text-encoding-functions.md#atlhexdecodegetrequiredlength)|Вызывайте эту функцию для получения размера (в байтах) буфера, который может содержать декодированные данные из шестнадцатеричной кодированной строки указанной длины.|  
|[AtlHexEncode](reference/atl-text-encoding-functions.md#atlhexencode)|Вызывайте эту функции для кодирования некоторых данных в виде строки шестнадцатеричного текста.|  
|[AtlHexEncodeGetRequiredLength](reference/atl-text-encoding-functions.md#atlhexencodegetrequiredlength)|Вызывайте эту функцию для получения размера (в символах) буфера, который может содержать строку, закодированную из данных указанного размера.|  
|[AtlUnicodeToUTF8](reference/atl-text-encoding-functions.md#atlunicodetoutf8)|Вызывайте эту функцию для преобразования строки Юникода в UTF-8.|  
|[BEncode](reference/atl-text-encoding-functions.md#bencode)|Вызывайте эту функцию для преобразования некоторых данных с использованием кодировки "B".|  
|[BEncodeGetRequiredLength](reference/atl-text-encoding-functions.md#bencodegetrequiredlength)|Вызывайте эту функцию для получения размера (в символах) буфера, который может содержать строку, закодированную из данных указанного размера.|  
|[EscapeXML](reference/atl-text-encoding-functions.md#escapexml)|Вызывайте эту функцию для преобразования символов, небезопасных для использования в XML, в их безопасные эквиваленты.|  
|[GetExtendedChars](reference/atl-text-encoding-functions.md#getextendedchars)|Вызывайте эту функцию для получения количества символов национального алфавита в строке.|  
|[IsExtendedChar](reference/atl-text-encoding-functions.md#isextendedchar)|Вызывайте эту функцию для определения, является ли заданный символ символом национального алфавита (меньше 32, больше 126 и не является символом табуляции, перевода строки или возврата каретки).|  
|[QEncode](reference/atl-text-encoding-functions.md#qencode)|Вызывайте эту функцию для преобразования некоторых данных с использованием кодировки "Q".|  
|[QEncodeGetRequiredLength](reference/atl-text-encoding-functions.md#qencodegetrequiredlength)|Вызывайте эту функцию для получения размера (в символах) буфера, который может содержать строку, закодированную из данных указанного размера.|  
|[QPDecode](reference/atl-text-encoding-functions.md#qpdecode)|Декодирует строку данных, которая была закодирована в quoted-printable формате, например предыдущим вызовом [QPEncode](reference/atl-text-encoding-functions.md#qpencode).|  
|[QPDecodeGetRequiredLength](reference/atl-text-encoding-functions.md#qpdecodegetrequiredlength)|Вызывайте эту функцию для получения размера (в байтах) буфера, который может содержать декодированные данные из строки указанной длины, закодированной в печатаемом формате с кавычками (quoted-printable).|  
|[QPEncode](reference/atl-text-encoding-functions.md#qpencode)|Вызывайте эту функцию для кодирования некоторых данных в печатаемом формате с кавычками (quoted-printable).|  
|[QPEncodeGetRequiredLength](reference/atl-text-encoding-functions.md#qpencodegetrequiredlength)|Вызывайте эту функцию для получения размера (в символах) буфера, который может содержать строку, закодированную из данных указанного размера.|  
|[UUDecode](reference/atl-text-encoding-functions.md#uudecode)|Декодирует строку данных, которая была закодирована в кодировке UUENCODE например предыдущим вызовом [UUEncode](reference/atl-text-encoding-functions.md#uuencode).|  
|[UUDecodeGetRequiredLength](reference/atl-text-encoding-functions.md#uudecodegetrequiredlength)|Вызывайте эту функцию для получения размера (в байтах) буфера, который может содержать декодированные данные из строки указанной длины в кодировке UUEncode.|  
|[UUEncode](reference/atl-text-encoding-functions.md#uuencode)|Вызывайте эту функцию для кодирования данных в кодировке UUEncode.|  
|[UUEncodeGetRequiredLength](reference/atl-text-encoding-functions.md#uuencodegetrequiredlength)|Вызывайте эту функцию для получения размера (в символах) буфера, который может содержать строку, закодированную из данных указанного размера.|  
  
## <a name="see-also"></a>См. также  
 [Основные понятия](../atl/active-template-library-atl-concepts.md)   
 [Компоненты ATL COM Desktop](../atl/atl-com-desktop-components.md)

