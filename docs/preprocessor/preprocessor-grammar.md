---
title: "Грамматика препроцессора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- preprocessor
- grammar, preprocessor
- preprocessor, grammar
ms.assetid: 6cd33fad-0b08-4592-9be8-7359c43e24e9
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 797d4bf4274a92ca4f265d01579698c0f9c6a4a3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="preprocessor-grammar"></a>Грамматика препроцессора
**#define***идентификатор* *строке токена*необязательно    
  
 *#***определить***идентификатор*[**(** *идентификатор*необ**,** *...*  **,** *идентификатор*необ **)**] *строке токена*необязательно    
  
 **определенные (***идентификатор* **)**   
  
 **определенные***идентификатор*   
  
 `#include`**»***-пути***»**  
  
 `#include` **\<**  *-пути***>**  
  
 **#line***последовательность цифр***»** *filename* **»**необязательно      
  
 *#***undef***идентификатор*   
  
 **#error***строке токена*   
  
 **#pragma***строке токена*   
  
 *Условное* :  
 *IF часть elif части*необ*else часть*необ*endif строка*  
  
 *IF часть* :  
 *Если linetext*  
  
 *Если строка* :  
 **#if***константное выражение*   
  
 **#ifdef***идентификатор*   
  
 **#ifndef***идентификатор*   
  
 *elif части* :  
 *текст elif строки*  
  
 *elif части elif строки текста*  
  
 *elif строки* :  
 **#elif***константное выражение*   
  
 *Else часть* :  
 *Else linetext*  
  
 *строки Else* :  
 `#else`  
  
 *ENDIF строка* :  
 `#endif`  
  
 *последовательность цифр* :  
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