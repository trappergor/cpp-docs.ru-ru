---
title: "Ошибка компилятора C2569 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2569
dev_langs: C++
helpviewer_keywords: C2569
ms.assetid: 092bed1e-f631-436c-9586-7750629f6fac
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e99e8192d12ed37cf6ec258df8c14f61003a750d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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