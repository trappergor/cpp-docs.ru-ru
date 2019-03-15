---
title: Советы по программированию многобайтовой кодировки
ms.date: 11/04/2016
helpviewer_keywords:
- programming [C++], MBCS
- character sets [C++], multibyte
- MBCS [C++], programming
- multibyte characters [C++]
ms.assetid: d8ad36b8-917f-474e-8adb-69462adecd17
ms.openlocfilehash: 420e376d3a66c8f8115732692089f4254847bc0d
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57808255"
---
# <a name="mbcs-programming-tips"></a>Советы по программированию многобайтовой кодировки

В новых разработках следует использовать кодировку Юникод для всех строк, которые конечные пользователи могут столкнуться возможно. MBCS — это устаревшая технология, который был замещен стандартом Юникода. В этом разделе содержатся советы для разработчиков, которые необходимо поддерживать существующие программы, которые используют MBCS и где нецелесообразно для преобразования в Юникод. Совет относится к MFC-приложения и приложения, созданные без использования MFC. Ниже приведен список разделов.

- [Общие советы по программированию многобайтовой кодировки](../text/general-mbcs-programming-advice.md)

- [Увеличение и уменьшение значений указателей](../text/incrementing-and-decrementing-pointers.md)

- [Индексы байтов](../text/byte-indices.md)

- [Последний символ в строке](../text/last-character-in-a-string.md)

- [Присваивание символов](../text/character-assignment.md)

- [Сравнение знаков](../text/character-comparison.md)

- [Переполнение буфера](../text/buffer-overflow.md)

## <a name="see-also"></a>См. также

[Поддержка многобайтовых кодировок](../text/support-for-multibyte-character-sets-mbcss.md)
