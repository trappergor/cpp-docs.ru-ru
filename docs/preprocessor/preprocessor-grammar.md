---
title: Грамматика препроцессора | Документация Майкрософт
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
ms.openlocfilehash: 1871d1b8281f4dd74733133ede70ed80430246b3
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/10/2018
ms.locfileid: "42538904"
---
# <a name="preprocessor-grammar"></a>Грамматика препроцессора
**#define***идентификатор* *строке токена*opt    
  
*#* **Определение***идентификатор*[**(** *идентификатор*opt **,** *...*  **,** *идентификатор*opt **)**] *строке токена*opt    
  
**определенные (***идентификатор* **)**   
  
**определенные***идентификатор*   
  
`#include` **"***path-spec***"**  
  
`#include` **\<***PATH-spec***>**  
  
**#line***последовательность цифр***"** *filename* **"** opt      
  
*#* **undef***идентификатор*   
  
**#error***строке токена*   
  
**#pragma***строке токена*   
  
*условный* :  
*IF часть elif части*opt*else часть*opt*endif строка*  
  
*IF часть* :  
*if-linetext*  
  
*строки IF* :  
**#if***константного выражения*   
  
**#ifdef***идентификатор*   
  
**#ifndef***идентификатор*   
  
*elif части* :  
*elif строка текста*  
  
*elif части elif строка текста*  
  
*elif строка* :  
**#elif***константного выражения*   
  
*Else часть* :  
*else-linetext*  
  
*Else строка* :  
`#else`  
  
*ENDIF строка* :  
`#endif`  
  
*последовательность цифр* :  
*digit*  
  
*digit-sequence digit*  
  
*цифра* : один из  
**0 1 2 3 4 5 6 7 8 9**  
  
*токен строки* :  
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
> Следующие Нетерминальные элементы в [лексические соглашения](../cpp/lexical-conventions.md) раздел *Справочник по языку C++*: `constant`, `constant` - *выражение* , *идентификатор*, *ключевое слово*, `operator`, и `punctuator`.  
  
## <a name="see-also"></a>См. также  
 
[Общие сведения о грамматике (C/C++)](../preprocessor/grammar-summary-c-cpp.md)