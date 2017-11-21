---
title: "Ошибка компилятора C2726 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2726
dev_langs: C++
helpviewer_keywords: C2726
ms.assetid: f0191bb7-c175-450b-bf09-a3213db96d09
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f97067f71927491072f303bc872616640bae3367
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2726"></a>Ошибка компилятора C2726
gcnew может использоваться только для создания объекта управляемого типа или типа WinRT  
  
 Невозможно создать экземпляр собственного типа в куче сбора мусора.  
  
 В следующем примере показано возникновение ошибки C2726 и приводятся сведения по ее устранению.  
  
```  
// C2726.cpp  
// compile with: /clr  
using namespace System;  
class U {};  
ref class V {};  
value class W {};  
  
int main() {  
   U* pU = gcnew U;    // C2726  
   U* pU2 = new U;   // OK  
   V^ p2 = gcnew V;   // OK  
   W p3;   // OK  
  
}  
```  
