---
title: Общие сведения об операторах | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: ce45d2fe-ec0e-459f-afb1-80ab6a7f0239
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4b2d3b27149344151f891e23c39bbecb8e4c1102
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32391354"
---
# <a name="summary-of-statements"></a>Общие сведения об операторах
*statement*:  
 *labeled-statement*  
  
 *compound-statement*  
  
 *expression-statement*  
  
 *selection-statement*  
  
 *iteration-statement*  
  
 *jump-statement*  
  
 *try-except-statement* /* относится только к системам Microsoft \*/  
  
 *try-finally-statement* /* относится только к системам Microsoft \*/  
  
 *оператор-перехода*:  
 **goto**  *identifier*  **;**  
  
 **continue ;**  
  
 **break ;**  
  
 **return**  *expression*opt **;**  
  
 *compound-statement*:  
 **{**  *declaration-list*opt*statement-list*opt **}**  
  
 *declaration-list*:  
 *declaration*  
  
 *declaration-list declaration*  
  
 *statement-list*:  
 *statement*  
  
 *statement-list statement*  
  
 *expression-statement*:  
 *expression*opt **;**  
  
 *оператор-итерации*:  
 **while (**  *expression*  **)**  *statement*  
  
 **do**  *statement*  **while (**  *expression*  **) ;**  
  
 **for (**  *expression*opt **;** *expression*opt **;** *expression*opt **)** *statement*  
  
 *selection-statement*:  
 **if (**  *expression*  **)**  *statement*  
  
 **if (**  *expression*  **)**  *statement*  **else**  *statement*  
  
 **switch (**  *expression*  **)**  *statement*  
  
 *labeled-statement*:  
 *identifier*  **:**  *statement*  
  
 **case**  *constant-expression*  **:**  *statement*  
  
 **default :**  *statement*  
  
 *try-except-statement*:   /\* относится только к системам Microsoft \*/  
 **__try**  *compound-statement*  
  
 **__except (**  *expression*  **)**  *compound-statement*  
  
 *try-finally-statement*:   /\* относится только к системам Microsoft \*/  
 **__try**  *compound-statement*  
  
 **__finally**  *compound-statement*  
  
## <a name="see-also"></a>См. также  
 [Грамматика структуры фразы](../c-language/phrase-structure-grammar.md)