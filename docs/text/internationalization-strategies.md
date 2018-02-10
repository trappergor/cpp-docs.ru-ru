---
title: "Стратегии международного использования | Документы Microsoft"
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
- language-portable code [C++]
- MBCS [C++], internationalization strategies
- Windows API [C++], international programming strategies
- Win32 [C++], international programming strategies
- Unicode [C++], globalizing applications
- character sets [C++], international programming strategies
- localization [C++], character sets
ms.assetid: b09d9854-0709-4b9a-a00c-b0b8bc4199b1
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ead6470bbbeacd43326f4373877eb991e5899116
ms.sourcegitcommit: a5916b48541f804a79891ff04e246628b5f9a24a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2018
---
# <a name="internationalization-strategies"></a>Стратегии международного использования
В зависимости от целевой ОС и рынков у вас есть несколько стратегии международного использования:  
  
-   В приложении используется Юникод.  
  
     С помощью функции Юникода и все символы имеют ширину 16 бит (несмотря на то, что для особых целей можно использовать символы ANSI в некоторых частях программы). Библиотеки времени выполнения C предоставляет функции, макросы и типы данных только для Юникода для программирования. MFC, полностью поддерживают Юникод.  
  
-   Приложение использует многобайтовой Кодировки и может быть запущен на любой платформе Win32.  
  
     Используется функциональность многобайтовой. Строки могут содержать однобайтовые и двухбайтовые символы. Библиотеки времени выполнения C предоставляет функции, макросы и типы данных только для многобайтовой Кодировки для программирования. MFC, полностью включены MBCS.  
  
-   Исходный код для приложения, написанные для полной переносимости — путем повторной компиляции с символом **_UNICODE** или символ **_MBCS** определен, можно создавать версии, использующие любой. Дополнительные сведения см. в разделе [универсальные текстовые сопоставления в файле Tchar.h](../text/generic-text-mappings-in-tchar-h.md).  
  
     Используется, чтобы полностью переносимые C во время выполнения функций, макросов и типы данных. MFC поддерживает все эти стратегии.  
  
 В оставшейся части этих разделов сосредоточиться на написание полностью переносимого кода, можно создавать в кодировке Юникод или как MBCS.  
  
## <a name="see-also"></a>См. также  
 [Юникод и многобайтовая Кодировка](../text/unicode-and-mbcs.md)   
 [Языковые стандарты и кодовые страницы](../text/locales-and-code-pages.md)