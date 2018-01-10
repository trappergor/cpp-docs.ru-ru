---
title: "Ошибка компилятора C3460 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3460
dev_langs: C++
helpviewer_keywords: C3460
ms.assetid: adbf8775-10ca-4654-acdf-58dd765351cd
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a1184cc382a6c7f19e9a3b080e9850fdf7df74be
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3460"></a>Ошибка компилятора C3460
"тип": только пользовательские типы могут перенаправляться  
  
 Дополнительные сведения см. в разделе [переадресации типов (C + +/ CLI)](../../windows/type-forwarding-cpp-cli.md).  
  
## <a name="example"></a>Пример  
 В следующем примере создается компонент.  
  
```  
// C3460.cpp  
// compile with: /LD /clr  
public ref class R {};  
```  
  
## <a name="example"></a>Пример  
 В следующем примере возникает ошибка C3460.  
  
```  
// C3460_b.cpp  
// compile with: /clr /c  
#using "C3460.dll"  
[assembly:TypeForwardedTo(int::typeid)];   // C3460  
[assembly:TypeForwardedTo(R::typeid)];  
```