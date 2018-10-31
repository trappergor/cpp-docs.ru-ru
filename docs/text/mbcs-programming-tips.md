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
ms.openlocfilehash: a88fffbfc42dd6e7386ec43e55f2013f2548b6f5
ms.sourcegitcommit: a3c9e7888b8f437a170327c4c175733ad9eb0454
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2018
ms.locfileid: "50204474"
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