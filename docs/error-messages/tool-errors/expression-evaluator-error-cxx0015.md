---
title: "Ошибка вычислителя выражений CXX0015 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: CXX0015
dev_langs: C++
helpviewer_keywords:
- CXX0015
- CAN0015
ms.assetid: 35efaf77-d578-48d8-bfc5-fdeb2a46a8b5
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d6b04fd2b13b2acd9021dcd8e751a0b4cbefd166
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="expression-evaluator-error-cxx0015"></a>Ошибка вычислителя выражений CXX0015
слишком сложное выражение (переполнение стека)  
  
 Введенное выражение был слишком сложно или имеет слишком глубокую объема памяти, доступной для вычислитель выражений C.  
  
 Переполнение обычно происходит из-за слишком большого количества незавершенных вычислений.  
  
 Изменить выражение, чтобы каждый компонент выражения вычислялись по мере его обнаружения, а не ждать другие части выражения вычисляется.  
  
 Разбейте выражение на несколько команд.  
  
 Эта ошибка идентична CAN0015.