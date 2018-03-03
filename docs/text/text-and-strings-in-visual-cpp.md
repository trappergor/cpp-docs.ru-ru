---
title: "Текст и строки в Visual C++ | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
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
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a911b3a4547be409047004969043943b54bb2480
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="text-and-strings-in-visual-c"></a>Текст и строки в Visual C++
Важным аспектом разработки приложений для международных рынков является соответствующее предоставление местных кодировок. Кодировка ASCII определяет символы в диапазоне от 0x00 до 0x7F. Существуют другие кодировки, в основном европейские, которые определяют символы в диапазоне от 0x00 до 0x7F одинаково в набор символов ASCII, а также определяют расширенную кодировку от 0x80 до 0xFF. Таким образом 8-разрядная версия, одиночные байтов кодировки (SBCS) достаточно для представления набора символов ASCII, а также кодировки для большинства европейских языков. Однако некоторые не европейские кодировки, например Кандзи (японский), включают намного больше символов, чем однобайтовая кодировка представления и поэтому требуют многобайтовой кодировки (MBCS).  
  
## <a name="in-this-section"></a>В этом разделе  
 [Юникод и многобайтовая кодировка](../text/unicode-and-mbcs.md)  
 Обсуждение поддержки Visual C++ для программирования Юникода и MBCS.  
  
 [Поддержка Юникода](../text/support-for-unicode.md)  
 Описывает Юникод, стандартом, поддерживающим все кодировки, включая наборы символов, которые не могут быть представлены одним байтом.  
  
 [Поддержка многобайтовой кодировки (MBCS)](../text/support-for-multibyte-character-sets-mbcss.md)  
 Описывает MBCS является альтернативой Юникоду для поддержки кодировок, подобных японской и китайской, которые не могут быть представлены одним байтом.  
  
 [Универсальные текстовые сопоставления в файле Tchar.h](../text/generic-text-mappings-in-tchar-h.md)  
 Предоставляет специфичные для Microsoft универсальные текстовые сопоставления для многих типов данных, подпрограмм и других объектов.  
  
 [Практическое руководство. Преобразование различных типов строк](../text/how-to-convert-between-various-string-types.md)  
 Демонстрирует преобразование различных типов строк Visual C++ в другие строки.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Интернационализация](../c-runtime-library/internationalization.md)  
 Описывает поддержку интернационализации в библиотеке времени выполнения C.  
  
 [Примеры интернационализации](http://msdn.microsoft.com/en-us/aa8d390c-cf4c-4dd8-9dea-74d81f93f2f8)  
 Ссылки на примеры, показывающие интернационализации в Visual C++.  
  
 [Locale Names, Languages, and Country/Region Strings](../c-runtime-library/locale-names-languages-and-country-region-strings.md) (Строки страны или региона и языка)  
 Предоставляет строки языка и страны или региона, в библиотеке времени выполнения C.