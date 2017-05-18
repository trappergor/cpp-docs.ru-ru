---
title: "Ошибка компилятора C2585 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2585
dev_langs:
- C++
helpviewer_keywords:
- C2585
ms.assetid: 05bb1a9c-28fb-4a88-a1b5-aea85ebdee1c
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
ms.openlocfilehash: ec9787e04d5c3539bf671a575a9487af94c3910d
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2585"></a>Ошибка компилятора C2585
явное преобразование к «типу» является неоднозначным  
  
 Преобразование типов может иметь несколько результатов.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.  
  
1.  Преобразование из типа класса или структуры на основе множественного наследования. Если тип наследует тот же базовый класс несколько раз, функция или оператор преобразования должны использовать разрешение области (`::`), чтобы указать, какие из этих классов для использования при преобразовании.  
  
2.  Оператор преобразования и конструктор определены сделать то же самое преобразование.
