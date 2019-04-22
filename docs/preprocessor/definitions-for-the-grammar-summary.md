---
title: Общие сведения об определениях для грамматики
ms.date: 11/04/2016
helpviewer_keywords:
- preprocessor, definitions
- preprocessor
ms.assetid: cc752dc8-6f4e-4347-a556-e0d9ef4c46bd
ms.openlocfilehash: 6e8671ba0d68b13f68db0f2b08dab4fe98f917e7
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59024959"
---
# <a name="definitions-for-the-grammar-summary"></a>Общие сведения об определениях для грамматики

Терминальные слова — это конечные точки в определении синтаксиса. Никакое другое разрешение невозможно. Терминальные слова включают в себя набор зарезервированных ключевых слов и определенные пользователем идентификаторы.

Нетерминальные слова — это местозаполнители в синтаксисе. Большая их часть определена в других местах этой сводки синтаксиса. Определения могут быть рекурсивными. Следующие Нетерминальные слова определены в [лексические соглашения](../cpp/lexical-conventions.md) раздел *Справочник по языку C++*:

`constant`, *constant-expression*, *identifier*, *keyword*, `operator`, `punctuator`

Необязательный компонент обозначается атрибутом <sub>opt</sub> в нижнем индексе. Например, ниже приведено необязательное выражение, заключенное в фигурные скобки:

**{** *expression*<sub>opt</sub> **}**

## <a name="see-also"></a>См. также

[Общие сведения о грамматике (C/C++)](../preprocessor/grammar-summary-c-cpp.md)