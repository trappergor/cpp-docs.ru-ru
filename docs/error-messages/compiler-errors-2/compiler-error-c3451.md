---
title: "Ошибка компилятора C3451 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3451
dev_langs:
- C++
helpviewer_keywords:
- C3451
ms.assetid: a4897a69-e3e7-40bb-bb1c-598644904012
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: c1c0f9de919fbe646eaa6303fa5b1e9fcba886eb
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3451"></a>Ошибка компилятора C3451
«атрибут»: невозможно применить неуправляемый атрибут для «тип»  
  
 Атрибут C++ не может применяться к типу CLR. В разделе [Справочник по атрибутам C++](../../windows/cpp-attributes-reference.md) для получения дополнительной информации.  
  
 Для получения дополнительной информации см. [User-Defined Attributes](../../windows/user-defined-attributes-cpp-component-extensions.md).  
  
 Эта ошибка может возникать в результате действий по обеспечению совместимости компилятора с Visual C++ 2005: [uuid](../../windows/uuid-cpp-attributes.md) атрибут больше не допускается для пользовательского атрибута, с помощью программирования в среде CLR. Взамен рекомендуется использовать <xref:System.Runtime.InteropServices.GuidAttribute> .  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C3451.  
  
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
