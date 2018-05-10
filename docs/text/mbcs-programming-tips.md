---
title: Советы по программированию многобайтовой Кодировки | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
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
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7eb6e298961580c959235a97f37793df41d1124f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
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