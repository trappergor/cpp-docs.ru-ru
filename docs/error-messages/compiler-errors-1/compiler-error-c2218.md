---
title: "Ошибка компилятора C2218 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2218
dev_langs:
- C++
helpviewer_keywords:
- C2218
ms.assetid: b0f55da4-8edb-4b45-b298-1a091981bd7b
caps.latest.revision: 9
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
ms.openlocfilehash: f3ece905f03dc788580afde3e526041e933e3072
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2218"></a>Ошибка компилятора C2218
__vectorcall не может использоваться с /arch:IA32  
  
 Соглашение о вызовах `__vectorcall` поддерживается только в машинном коде для процессоров x86 и x64, в которых используется набор инструкций SSE2 и выше. Дополнительные сведения см. в разделе [__vectorcall](../../cpp/vectorcall.md).  
  
 Чтобы устранить эту ошибку, измените параметры компилятора на целевые наборы инструкций SSE2, AVX или AVX2. Дополнительные сведения см. в разделе [/arch (x86)](../../build/reference/arch-x86.md).
