---
title: Определения для сведения о грамматике | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- preprocessor, definitions
- preprocessor
ms.assetid: cc752dc8-6f4e-4347-a556-e0d9ef4c46bd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0ac3b742406f1e8be955921a9ee238f3b35d3bdf
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/10/2018
ms.locfileid: "42539103"
---
# <a name="definitions-for-the-grammar-summary"></a>Общие сведения об определениях для грамматики
Терминальные слова — это конечные точки в определении синтаксиса. Никакое другое разрешение невозможно. Терминальные слова включают в себя набор зарезервированных ключевых слов и определенные пользователем идентификаторы.  
  
Нетерминальные слова — это местозаполнители в синтаксисе. Большая их часть определена в других местах этой сводки синтаксиса. Определения могут быть рекурсивными. Следующие Нетерминальные слова определены в [лексические соглашения](../cpp/lexical-conventions.md) раздел *Справочник по языку C++*:  
  
`constant`, *константное_выражение*, *идентификатор*, *ключевое слово*, `operator`, `punctuator`  
  
Необязательный компонент указывается нижним индексом "необ.". Например, ниже приведено необязательное выражение, заключенное в фигурные скобки:  
  
**{** *выражение*opt **}**  
  
## <a name="see-also"></a>См. также 
 
[Общие сведения о грамматике (C/C++)](../preprocessor/grammar-summary-c-cpp.md)