---
title: Ошибка компилятора C3076 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3076
dev_langs:
- C++
helpviewer_keywords:
- C3076
ms.assetid: 8a87b3e4-2c17-4b87-9622-ef0962d6a34e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 465dd45c4ddfc41e3ba7a059619028711d6f73e2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33247583"
---
# <a name="compiler-error-c3076"></a>Ошибка компилятора C3076
«экземпляр»: нельзя внедрить экземпляр ссылочного типа «тип» в собственном типе  
  
 Неуправляемый тип не может содержать экземпляр типа CLR.  
  
 Дополнительные сведения см. в разделе [семантика стека C++ для ссылочных типов](../../dotnet/cpp-stack-semantics-for-reference-types.md).  
  
## <a name="example"></a>Пример  
 В следующем примере возникает ошибка C3076.  
  
```  
// C3076.cpp  
// compile with: /clr /c  
ref struct U {};  
  
struct V {  
   U y;   // C3076  
};  
  
ref struct W {  
   U y;   // OK  
};  
```