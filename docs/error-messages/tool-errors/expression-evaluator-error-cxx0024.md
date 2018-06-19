---
title: Ошибка вычислителя выражений CXX0024 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0024
dev_langs:
- C++
helpviewer_keywords:
- CXX0024
- CAN0024
ms.assetid: eca6adbd-8ff2-4f51-a1cc-a2e9d5d0a47d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 50a07297ddabf269b003a1f14d967d1187fea96d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33302465"
---
# <a name="expression-evaluator-error-cxx0024"></a>Ошибка вычислителя выражений CXX0024
операции требуется l значение  
  
 Выражение, результатом вычисления не l значением указан для операции, требующей l значением.  
  
 L значение (называемое так, потому что он отображается в левой части оператора присваивания) — это выражение, который ссылается на расположение в памяти.  
  
 Например `buffer[count]` является допустимым l значением, потому что он указывает конкретное расположение в памяти. Логическое сравнение `zed != 0` не является допустимым l значением, так как его результатом является значение TRUE или FALSE, а не на адрес в памяти.  
  
 Эта ошибка идентична ошибке CAN0024.