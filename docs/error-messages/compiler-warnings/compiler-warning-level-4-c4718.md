---
title: "Компилятор C4718 предупреждение (уровень 4) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4718
dev_langs:
- C++
helpviewer_keywords:
- C4718
ms.assetid: 29507f8a-b024-42c1-a3b8-f35d1f2641f3
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 48a1144d19f760760f40b5bd9fd1cb43e00e11d8
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-4-c4718"></a>Предупреждение компилятора (уровень 4) C4718
"вызов_функции": рекурсивный вызов не имеет побочных эффектов; удаление  
  
 Функция содержит рекурсивный вызов, но с другой стороны побочные эффекты отсутствуют. Вызов этой функции удаляется. Это повлияет на поведение программы, но не на ее правильность. В то время как оставленный вызов может привести к исключению переполнения стека, удаление этого вызова устраняет такую возможность.
