---
title: Ошибка компилятора C2569 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2569
dev_langs:
- C++
helpviewer_keywords:
- C2569
ms.assetid: 092bed1e-f631-436c-9586-7750629f6fac
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4869f13d972cea80bd590633b3aae2ea0c96f392
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33230346"
---
# <a name="compiler-error-c2569"></a>Ошибка компилятора C2569
«EnumOrUnion»: перечисление или объединение не может использоваться как базовый класс  
  
 Если тип должен быть производным от указанного объединения или перечисления, измените объединения или перечисления для класса или структуры.  
  
 Следующий пример приводит к возникновению ошибки C2569:  
  
```  
// C2569.cpp  
// compile with: /c  
union ubase {};  
class cHasPubUBase : public ubase {};   // C2569  
// OK  
struct sbase {};  
class cHasPubUBase : public sbase {};  
```