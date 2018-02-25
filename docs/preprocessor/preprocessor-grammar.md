---
title: "Грамматика препроцессора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- preprocessor
- grammar, preprocessor
- preprocessor, grammar
ms.assetid: 6cd33fad-0b08-4592-9be8-7359c43e24e9
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 02b3597b035e3ea4bfa1670aa405109f4c01a077
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="preprocessor-grammar"></a>Грамматика препроцессора
**#define**  *identifier* *token-string*opt  
  
 *#* **Определение***идентификатор*[**(** *идентификатор*необ**,** *...*  **,** *идентификатор*необ **)**] *строке токена*необязательно    
  
 **defined(**  *identifier* **)**  
  
 **defined**  *identifier*  
  
 `#include` **"***path-spec***"**  
  
 `#include` **\<***path-spec***>**  
  
 **#line**  *digit-sequence*  **"** *filename* **"**opt  
  
 *#* **undef***идентификатор*   
  
 **#error**  *token-string*  
  
 **#pragma**  *token-string*  
  
 *Условное* :  
 *IF часть elif части*необ*else часть*необ*endif строка*  
  
 *IF часть* :  
 *if-linetext*  
  
 *Если строка* :  
 **#if**  *constant-expression*  
  
 **#ifdef***идентификатор*   
  
 **#ifndef***идентификатор*   
  
 *elif части* :  
 *текст elif строки*  
  
 *elif части elif строки текста*  
  
 *elif строки* :  
 **#elif**  *constant-expression*  
  
 *else-part* :  
 *else-linetext*  
  
 *строки Else* :  
 `#else`  
  
 *ENDIF строка* :  
 `#endif`  
  
 *digit-sequence* :  
 *digit*  
  
 *digit-sequence digit*  
  
 *цифра* : один из  
 **0 1 2 3 4 5 6 7 8 9**  
  
 *маркер строки* :  
 Строка токенов  
  
 *токен* :  
 *keyword*  
  
 *identifier*  
  
 *constant*  
  
 *operator*  
  
 `punctuator`  
  
 *Имя файла* :  
 Допустимое имя файла в ОС  
  
 *PATH-spec* :  
 Допустимый путь к файлу  
  
 *текст* :  
 Любая текстовая последовательность  
  
> [!NOTE]
>  Следующие Нетерминальные элементы рассматриваются в [лексические соглашения](../cpp/lexical-conventions.md) раздел *Справочник по языку C++*: `constant`, `constant` - *выражение* , *идентификатор*, *ключевое слово*, `operator`, и `punctuator`.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о грамматике (C/C++)](../preprocessor/grammar-summary-c-cpp.md)