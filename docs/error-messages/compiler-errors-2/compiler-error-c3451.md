---
title: "Ошибка компилятора C3451 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3451"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3451"
ms.assetid: a4897a69-e3e7-40bb-bb1c-598644904012
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# Ошибка компилятора C3451
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"атрибут": к "тип" невозможно применить неуправляемый атрибут  
  
 Атрибут C\+\+ не может быть применен к типу CLR.  Дополнительные сведения см. в разделе [C\+\+ Attributes Reference](../../windows/cpp-attributes-reference.md).  
  
 Для получения дополнительной информации см. [Пользовательские атрибуты](../../windows/user-defined-attributes-cpp-component-extensions.md).  
  
 Это ошибка может возникать в результате действий по обеспечению совместимости компилятора с Visual C\+\+ 2005: атрибут [uuid](../../windows/uuid-cpp-attributes.md) больше не разрешается применять в пользовательском атрибуте при использовании программирования в среде CLR.  Взамен рекомендуется использовать <xref:System.Runtime.InteropServices.GuidAttribute>.  
  
## Пример  
 В следующем примере продемонстрировано возникновение ошибки C3451.  
  
```  
// C3451.cpp  
// compile with: /clr /c  
using namespace System;  
[ attribute(AttributeTargets::All) ]  
public ref struct MyAttr {};  
  
[ MyAttr, helpstring("test") ]   // C3451  
// try the following line instead  
// [ MyAttr ]  
public ref struct ABC {};  
```