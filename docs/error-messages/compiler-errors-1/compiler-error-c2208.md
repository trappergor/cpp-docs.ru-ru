---
title: Ошибка компилятора C2208 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2208
dev_langs:
- C++
helpviewer_keywords:
- C2208
ms.assetid: 9ae704bc-bf70-45f1-8e47-0470f21edd4e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 24377d17735fc63e9dc0541dfd9fb432eb0e0cda
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33172113"
---
# <a name="compiler-error-c2208"></a>Ошибка компилятора C2208
«Тип»: нет членов, определенных с помощью этого типа  
  
 — Идентификатор, разрешающийся в имя типа в объявлении агрегата, но компилятор не может объявить член.  
  
 Следующий пример приводит к возникновению ошибки C2208:  
  
```  
// C2208.cpp  
class C {  
   C;   // C2208  
   C(){}   // OK  
};  
```