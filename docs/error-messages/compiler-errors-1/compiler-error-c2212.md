---
title: "Ошибка компилятора C2212 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2212
dev_langs:
- C++
helpviewer_keywords:
- C2212
ms.assetid: 3fdab304-272c-4d07-bfd4-fad75170e536
caps.latest.revision: 7
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
ms.openlocfilehash: d1aa06c7bebe066107b1d7e2ff9ca87c6a99fd08
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2212"></a>Ошибка компилятора C2212
«Идентификатор»: __based недоступен для указателей на функции  
  
 Указатели на функции не могут объявляться `__based`. Если требуются данные на основе кода, используйте `__declspec` ключевое слово или `data_seg` pragma.
