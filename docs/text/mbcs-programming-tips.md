---
title: Советы по программированию многобайтовой Кодировки | Документация Майкрософт
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ac4ed378640942dbe33490d618cec7289125b0c8
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46418792"
---
# <a name="mbcs-programming-tips"></a>Советы по программированию многобайтовой кодировки

В новых разработках следует использовать кодировку Юникод для всех строк, которые конечные пользователи могут столкнуться возможно. MBCS — это устаревшая технология, которая была заменена Юникода. В этом разделе содержатся советы для разработчиков, которые необходимо поддерживать существующие программы, которые используют MBCS и где нецелесообразно для преобразования в Юникод. Совет относится к MFC-приложения и приложения, созданные без использования MFC. Ниже приведен список разделов.

- [Общие советы по программированию многобайтовой кодировки](../text/general-mbcs-programming-advice.md)

- [Увеличение и уменьшение значений указателей](../text/incrementing-and-decrementing-pointers.md)

- [Индексы байтов](../text/byte-indices.md)

- [Последний символ в строке](../text/last-character-in-a-string.md)

- [Присваивание символов](../text/character-assignment.md)

- [Сравнение знаков](../text/character-comparison.md)

- [Переполнение буфера](../text/buffer-overflow.md)

## <a name="see-also"></a>См. также

[Поддержка многобайтовых кодировок](../text/support-for-multibyte-character-sets-mbcss.md)