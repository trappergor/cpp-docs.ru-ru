---
title: Ошибка вычислителя выражений CXX0039 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0039
dev_langs:
- C++
helpviewer_keywords:
- CXX0039
- CAN0039
ms.assetid: 8bf698d2-e015-4595-944f-72b81aa43d22
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8681d73d2889433516b205a47c500193bbeabdb0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="expression-evaluator-error-cxx0039"></a>Ошибка вычислителя выражений CXX0039
символ является неоднозначным  
  
 Вычислитель выражений C не может определить, какой экземпляр символа необходимо использовать в выражении. Символ возникает несколько раз в дереве наследования.  
  
 Необходимо использовать оператор разрешения области (`::`) для явного указания экземпляра для использования в выражении.  
  
 Эта ошибка идентична ошибке CAN0039.