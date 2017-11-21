---
title: "Ошибка компилятора C2605 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2605
dev_langs: C++
helpviewer_keywords: C2605
ms.assetid: a0e6f132-5acf-4e19-b277-ddf196d182bf
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 48b55b06f0d6af12f4b0476bc604089b043ae8a9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2605"></a>Ошибка компилятора C2605
name: этот метод зарезервирован в управляемом классе или классе WinRT  
  
 Определенные имена зарезервированы компилятором для внутренних функций.  Дополнительные сведения см. в разделе [деструкторы и методы завершения](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C2605:  
  
```  
// C2605.cpp  
// compile with: /clr /c  
ref class R {  
protected:  
   void Finalize() {}   // C2605  
};  
```