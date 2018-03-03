---
title: "Ошибка вычислителя выражений CXX0024 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- CXX0024
dev_langs:
- C++
helpviewer_keywords:
- CXX0024
- CAN0024
ms.assetid: eca6adbd-8ff2-4f51-a1cc-a2e9d5d0a47d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c96bd943719afb0d974a5c4386742bea24396fd4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="expression-evaluator-error-cxx0024"></a>Ошибка вычислителя выражений CXX0024
операции требуется l значение  
  
 Выражение, результатом вычисления не l значением указан для операции, требующей l значением.  
  
 L значение (называемое так, потому что он отображается в левой части оператора присваивания) — это выражение, который ссылается на расположение в памяти.  
  
 Например `buffer[count]` является допустимым l значением, потому что он указывает конкретное расположение в памяти. Логическое сравнение `zed != 0` не является допустимым l значением, так как его результатом является значение TRUE или FALSE, а не на адрес в памяти.  
  
 Эта ошибка идентична ошибке CAN0024.