---
title: Ошибка компилятора C3453 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3453
dev_langs:
- C++
helpviewer_keywords:
- C3453
ms.assetid: dbefdbcf-f697-4239-b7a5-1d99b85e9e7f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3f21a5833c618c5a5dfcc9ff2b608c5ec15bd1aa
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3453"></a>Ошибка компилятора C3453
"атрибут": атрибут неприменим из-за несоответствия квалификатора "сборка"  
  
 Атрибуты уровня сборки или модуля можно указывать только как отдельные инструкции.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C3453:  
  
```  
// C3453.cpp  
// compile with: /clr /c  
[assembly:System::CLSCompliant(true)]   // C3453  
// try the following line instead  
// [assembly:System::CLSCompliant(true)];  
ref class X {};  
```