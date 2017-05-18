---
title: "Предупреждение (уровень 1) C4124 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4124
dev_langs:
- C++
helpviewer_keywords:
- C4124
ms.assetid: c08c3a65-9584-47a1-a147-44f00c4b230e
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 8f367d8ec2360939d499c9f4e53ee690f860cc18
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4124"></a>Предупреждение (уровень 1) C4124 компилятора
использование __fastcall с проверкой стека неэффективно  
  
 `__fastcall` Ключевое слово было использовано при включенном режиме проверки стека.  
  
 `__fastcall` Соглашение создает код быстрее, но проверка стека замедляет. При использовании `__fastcall`, отключить проверку стека с **check_stack** pragma или/GS.  
  
 Это предупреждение выдается только для первой функции, объявленной в этих условиях.
