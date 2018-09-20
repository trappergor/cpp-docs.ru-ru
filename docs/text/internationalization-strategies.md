---
title: Стратегии международного использования | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- globalization [C++], character sets
- language-portable code [C++]
- MBCS [C++], internationalization strategies
- Windows API [C++], international programming strategies
- Win32 [C++], international programming strategies
- Unicode [C++], globalizing applications
- character sets [C++], international programming strategies
- localization [C++], character sets
ms.assetid: b09d9854-0709-4b9a-a00c-b0b8bc4199b1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d630aa39cb4eb4e56a0d64446ac5a5ea7a67881c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46395860"
---
# <a name="internationalization-strategies"></a>Стратегии международного использования

В зависимости от целевых операционных систем и рынков у вас есть несколько стратегии международного использования:

- Приложение использует формат Юникод.

   С помощью функции Юникода и все символы имеют ширину 16 бит (несмотря на то, что в некоторых частях программы можно использовать символы ANSI для особых целей). Библиотеки времени выполнения C предоставляет функции, макросы и типы данных только для Юникода для программирования. MFC, полностью поддерживает Юникод.

- Приложение использует MBCS и могут выполняться на любой платформе Win32.

   Используется функциональность многобайтовой. Строки могут содержать символы однобайтовые и двухбайтовые символы. Библиотеки времени выполнения C предоставляет функции, макросы и типы данных только для многобайтовой Кодировки для программирования. MFC – полностью многобайтовую.

- Исходный код для приложения, написанные для полной переносимости — путем перекомпиляции с символом `_UNICODE` или символ `_MBCS` определены, можно создавать версии, использующие любой. Дополнительные сведения см. в разделе [универсальные текстовые сопоставления в файле Tchar.h](../text/generic-text-mappings-in-tchar-h.md).

   Использовании полностью перенести C времени выполнения функции, макросы и типы данных. MFC поддерживает любой из этих стратегий.

В оставшейся части в этих разделах сосредоточиться на написании полностью переносимого кода, который можно создать в Юникоде, так и MBCS.

## <a name="see-also"></a>См. также

[Юникод и многобайтовая кодировка](../text/unicode-and-mbcs.md)<br/>
[Языковые стандарты и кодовые страницы](../text/locales-and-code-pages.md)