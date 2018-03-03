---
title: "Советы по программированию многобайтовой Кодировки | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _mbcs
dev_langs:
- C++
helpviewer_keywords:
- programming [C++], MBCS
- character sets [C++], multibyte
- MBCS [C++], programming
- multibyte characters [C++]
ms.assetid: d8ad36b8-917f-474e-8adb-69462adecd17
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1dc9c5dfd0dafe96e2d37b789b64c8215aa454e3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="mbcs-programming-tips"></a>Советы по программированию многобайтовой кодировки
В новых разработках следует использовать кодировку символов Юникода для всех строк, которые конечные пользователи могут видеть возможно. MBCS — это устаревшая технология, которая была заменена Юникода. В этом разделе содержатся советы для разработчиков, которые необходимо поддерживать существующие программы, которые используют многобайтовой Кодировки и где непрактично для преобразования в Юникод. Эти советы применимы к MFC-приложения и приложения, созданные без использования MFC. Ниже приведен список разделов.  
  
-   [Общие советы по программированию многобайтовой кодировки](../text/general-mbcs-programming-advice.md)  
  
-   [Увеличение и уменьшение значений указателей](../text/incrementing-and-decrementing-pointers.md)  
  
-   [Индексы байтов](../text/byte-indices.md)  
  
-   [Последний символ в строке](../text/last-character-in-a-string.md)  
  
-   [Присваивание символов](../text/character-assignment.md)  
  
-   [Сравнение знаков](../text/character-comparison.md)  
  
-   [Переполнение буфера](../text/buffer-overflow.md)  
  
## <a name="see-also"></a>См. также  
 [Поддержка многобайтовых кодировок](../text/support-for-multibyte-character-sets-mbcss.md)