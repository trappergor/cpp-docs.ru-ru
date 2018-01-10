---
title: "Ошибка компилятора C2218 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2218
dev_langs: C++
helpviewer_keywords: C2218
ms.assetid: b0f55da4-8edb-4b45-b298-1a091981bd7b
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cce36d9e8d4e8f2ac82ddec9a967ac7e045b4a03
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2218"></a>Ошибка компилятора C2218
__vectorcall не может использоваться с /arch:IA32  
  
 Соглашение о вызовах `__vectorcall` поддерживается только в машинном коде для процессоров x86 и x64, в которых используется набор инструкций SSE2 и выше. Дополнительные сведения см. в разделе [__vectorcall](../../cpp/vectorcall.md).  
  
 Чтобы устранить эту ошибку, измените параметры компилятора на целевые наборы инструкций SSE2, AVX или AVX2. Дополнительные сведения см. в разделе [/arch (x86)](../../build/reference/arch-x86.md).