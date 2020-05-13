---
title: Текст и строки в Visual C++
ms.date: 11/04/2016
helpviewer_keywords:
- globalization [C++], character sets
- programming [C++], international
- multiple language support [C++]
- Unicode [C++]
- international applications [C++], about international applications
- portability [C++]
- translation [C++], character sets
- non-European characters [C++]
- character sets [C++]
- globalization [C++]
- Japanese characters [C++]
- Kanji character support [C++]
- local character sets [C++]
- ASCII characters [C++]
- character sets [C++], about character sets
- localization [C++], character sets
- translating code [C++]
- localization [C++]
- character sets [C++], non-European
- portability [C++], character sets
- MBCS [C++], international programming
ms.assetid: a1bb27ac-abe5-4c6b-867d-f761d4b93205
ms.openlocfilehash: 80b7139996fddc82b206828d4a036922fa1446d5
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80167606"
---
# <a name="text-and-strings-in-visual-c"></a>Текст и строки в Visual C++

Важным аспектом разработки приложений для международных рынков является адекватное представление локальных наборов символов. Кодировка ASCII определяет символы в диапазоне от 0x00 до 0x7F. Существуют другие наборы символов, в основном европейские, которые определяют символы в диапазоне от 0x00 до 0x7F, идентичные кодировке ASCII, а также определяют расширенный набор символов от 0x80 до 0xFF. Таким образом, 8-разрядная однобайтовая кодировка (SBCS) достаточно для представления набора символов ASCII, а также наборов символов для многих европейских языков. Однако некоторые неевропейские кодировки, такие как японский символ кандзи, содержат гораздо больше символов, чем может представлять однобайтовую схему кодирования, и поэтому требует кодирования многобайтовой кодировки (MBCS).

## <a name="in-this-section"></a>в этом разделе

[Юникод и многобайтовая кодировка](../text/unicode-and-mbcs.md)<br/>
Обсуждается визуальная C++ поддержка программирования в Юникоде и многобайтовой кодировке.

[Поддержка Юникода](../text/support-for-unicode.md)<br/>
Описывает Юникод, спецификацию для поддержки всех наборов символов, включая наборы символов, которые не могут быть представлены в одном байте.

[Поддержка многобайтовых кодировок (MBCS)](../text/support-for-multibyte-character-sets-mbcss.md)<br/>
Обсуждается многобайтовая кодировка, альтернатива Юникоду для поддержки наборов символов, таких как японский и китайский, которые не могут быть представлены в одном байте.

[Универсальные текстовые сопоставления в файле tchar.h](../text/generic-text-mappings-in-tchar-h.md)<br/>
Предоставляет универсальные текстовые сопоставления, связанные с Майкрософт, для многих типов данных, подпрограмм и других объектов.

[Практическое руководство. Преобразование различных типов строк](../text/how-to-convert-between-various-string-types.md)<br/>
Демонстрирует преобразование различных визуальных C++ строковых типов в другие строки.

## <a name="related-sections"></a>См. также

[Интернационализация](../c-runtime-library/internationalization.md)<br/>
Обсуждается международная поддержка в библиотеке времени выполнения C.

[Международные примеры](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/International)<br/>
Ссылки на примеры, демонстрирующие многоязыковую поддержку C++в Visual.

[Locale Names, Languages, and Country/Region Strings](../c-runtime-library/locale-names-languages-and-country-region-strings.md) (Строки страны или региона и языка)<br/>
Предоставляет строки языка и страны или региона в библиотеке времени выполнения C.
