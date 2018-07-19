---
title: Ошибка компилятора C2261 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2261
dev_langs:
- C++
helpviewer_keywords:
- C2261
ms.assetid: 60969482-9e83-49b5-9631-a04bc844da12
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 45050daf3149cd813fb23b5814be5fe49c375f03
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33170470"
---
# <a name="compiler-error-c2261"></a>Ошибка компилятора C2261
«Строка»: ссылка на сборку, является недопустимым и не может быть разрешена  
  
 Значение не является допустимым.  
  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> используется для указания дружественной сборки. Например, если указать в качестве дружественной сборки b.dll a.dll, следует указать (в a.dll): InternalsVisibleTo("b"). Затем среда выполнения позволяет b.dll полный доступ к a.dll (за исключением частных типов).  
  
 Дополнительные сведения об использовании правильного синтаксиса при указании дружественных сборок см [дружественные сборки (C++)](../../dotnet/friend-assemblies-cpp.md).  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C2261.  
  
```  
// C2261.cpp  
// compile with: /clr /c  
using namespace System::Runtime::CompilerServices;  
[assembly: InternalsVisibleTo("a,a,a")];   // C2261  
[assembly: InternalsVisibleTo("a.a")];   // OK  
[assembly: InternalsVisibleTo("a")];   // OK  
```