---
title: "Ошибка компилятора C2218 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
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
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 3ca2e431fdfeff3c9dc957bee46f84cfd2c04162
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2218"></a>Ошибка компилятора C2218
__vectorcall не может использоваться с /arch:IA32  
  
 Соглашение о вызовах `__vectorcall` поддерживается только в машинном коде для процессоров x86 и x64, в которых используется набор инструкций SSE2 и выше. Дополнительные сведения см. в разделе [__vectorcall](../../cpp/vectorcall.md).  
  
 Чтобы устранить эту ошибку, измените параметры компилятора на целевые наборы инструкций SSE2, AVX или AVX2. Дополнительные сведения см. в разделе [/arch (x86)](../../build/reference/arch-x86.md).
