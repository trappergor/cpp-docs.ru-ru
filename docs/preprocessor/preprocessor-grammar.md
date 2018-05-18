---
title: Грамматика препроцессора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- preprocessor
- grammar, preprocessor
- preprocessor, grammar
ms.assetid: 6cd33fad-0b08-4592-9be8-7359c43e24e9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d14a3e00e18a2d3ac69dd472ac4056a379ada224
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="preprocessor-grammar"></a>Грамматика препроцессора
**#define***идентификатор* *строке токена*необязательно    
  
 *#* **Определение***идентификатор*[**(** *идентификатор*необ **,** *...*  **,** *идентификатор*необ **)**] *строке токена*необязательно  
  
 **определенные (***идентификатор* **)**   
  
 **определенные***идентификатор*   
  
 `#include` **«***-пути***»**  
  
 `#include` **\<***-пути***>**  
  
 **#line***последовательность цифр***»** *filename* **»**необязательно      
  
 *#* **undef***идентификатор*  
  
 **#error***строке токена*   
  
 **#pragma***строке токена*   
  
 *Условное* :  
 *IF часть elif части*необ*else часть*необ*endif строка*  
  
 *IF часть* :  
 *if-linetext*  
  
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
 *else-linetext*  
  
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