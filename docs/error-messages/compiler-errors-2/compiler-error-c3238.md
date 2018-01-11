---
title: "Ошибка компилятора C3238 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3238
dev_langs: C++
helpviewer_keywords: C3238
ms.assetid: 19942497-b3c5-4df0-9144-142ced92468b
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e729e0da83638c93dd7e79a55bc0960590f93f08
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3238"></a>Ошибка компилятора C3238
"тип": тип с этим именем уже перенаправлен в сборку "сборка"  
  
 В клиентском приложении был определен тип, который также определен посредством синтаксиса перенаправления в связанной сборке. Нельзя определять оба типа в области приложения.  
  
 В разделе [переадресации типов (C + +/ CLI)](../../windows/type-forwarding-cpp-cli.md) для получения дополнительной информации.  
  
## <a name="example"></a>Пример  
 В следующем примере создается сборка, содержащая тип, перенаправленный из другой сборки.  
  
```  
// C3238.cpp  
// compile with: /clr /LD  
public ref class R {};  
```  
  
## <a name="example"></a>Пример  
 В следующем примере создается сборка, которая используется для содержания определения типа, но содержит не только синтаксис перенаправления для типа.  
  
```  
// C3238_b.cpp  
// compile with: /clr /LD  
#using "C3238.dll"  
[ assembly:TypeForwardedTo(R::typeid) ];  
```  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C3238.  
  
```  
// C3238_c.cpp  
// compile with: /clr /c  
// C3238 expected  
// Delete the following line to resolve.  
#using "C3238_b.dll"  
public ref class R {};  
```