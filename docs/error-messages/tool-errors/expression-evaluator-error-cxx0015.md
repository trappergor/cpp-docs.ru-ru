---
title: Ошибка вычислителя выражений CXX0015 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0015
dev_langs:
- C++
helpviewer_keywords:
- CXX0015
- CAN0015
ms.assetid: 35efaf77-d578-48d8-bfc5-fdeb2a46a8b5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 945dbda4759fa2989acb0411d1a3216a5e9a036c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33297613"
---
# <a name="expression-evaluator-error-cxx0015"></a>Ошибка вычислителя выражений CXX0015
слишком сложное выражение (переполнение стека)  
  
 Введенное выражение был слишком сложно или имеет слишком глубокую объема памяти, доступной для вычислитель выражений C.  
  
 Переполнение обычно происходит из-за слишком большого количества незавершенных вычислений.  
  
 Изменить выражение, чтобы каждый компонент выражения вычислялись по мере его обнаружения, а не ждать другие части выражения вычисляется.  
  
 Разбейте выражение на несколько команд.  
  
 Эта ошибка идентична CAN0015.