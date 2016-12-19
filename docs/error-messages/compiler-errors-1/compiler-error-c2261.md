---
title: "Ошибка компилятора C2261 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2261"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2261"
ms.assetid: 60969482-9e83-49b5-9631-a04bc844da12
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2261
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"строка": ссылка на сборку недопустима и не может быть разрешена  
  
 Недопустимое значение.  
  
 Объект <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> используется для указания дружественной сборки.  Например, если  необходимо указать b.dll в качестве дружественной сборки для a.dll, следует указать \(в a.dll\): InternalsVisibleTo\("b"\).  Среда выполнения в этом случае разрешает b.dll полный доступ к a.dll \(за исключением частных типов\).  
  
 Дополнительные сведения об использовании правильного синтаксиса при указании дружеских сборок  см. в разделе [Дружественные сборки \(C\+\+\)](../../dotnet/friend-assemblies-cpp.md).  
  
## Пример  
 Следующий пример демонстрирует причины возникновения ошибки C2261.  
  
```  
// C2261.cpp  
// compile with: /clr /c  
using namespace System::Runtime::CompilerServices;  
[assembly: InternalsVisibleTo("a,a,a")];   // C2261  
[assembly: InternalsVisibleTo("a.a")];   // OK  
[assembly: InternalsVisibleTo("a")];   // OK  
```