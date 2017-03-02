---
title: "Ошибка вычислителя выражений CXX0015 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- CXX0015
dev_langs:
- C++
helpviewer_keywords:
- CXX0015
- CAN0015
ms.assetid: 35efaf77-d578-48d8-bfc5-fdeb2a46a8b5
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 22b4db607b40f73cc5c240b7fd75f5230832ec0f
ms.lasthandoff: 02/24/2017

---
# <a name="expression-evaluator-error-cxx0015"></a>Ошибка вычислителя выражений CXX0015
слишком сложное выражение (переполнение стека)  
  
 Введенное выражение было слишком сложно или имеет слишком глубоко объема памяти, доступной для вычислителя выражения C.  
  
 Переполнение обычно происходит из-за слишком большого количества незавершенных вычислений.  
  
 Изменить выражение, чтобы каждый компонент выражения вычислялись по мере его обнаружения, а не ждать другие части выражения необходимо вычислить.  
  
 Разбейте выражение на несколько команд.  
  
 Эта ошибка идентична CAN0015.
