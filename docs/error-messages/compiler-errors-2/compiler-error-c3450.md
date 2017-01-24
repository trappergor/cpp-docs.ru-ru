---
title: "Compiler Error C3450 | Microsoft Docs"
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
  - "C3450"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3450"
ms.assetid: 78892cf7-0b82-4589-90d0-e06666247003
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Compiler Error C3450
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

type: не атрибут; нельзя указать \[System::AttributeUsageAttribute\] или \[Windows::Foundation::Metadata::AttributeUsageAttribute\]  
  
 Заданный пользователем управляемый атрибут должен наследовать от <xref:System.ComponentModel.AttributeCollection.%23ctor%2A>.  Атрибут среды выполнения Windows должен быть определен в пространстве имен `Windows::Foundation::Metadata`.  
  
 Дополнительные сведения см. в разделе [Пользовательские атрибуты](../../windows/user-defined-attributes-cpp-component-extensions.md).  
  
## Пример  
 В следующем примере показано возникновение ошибки C3450 и приводятся сведения по ее устранению.  
  
```  
// C3450.cpp  
// compile with: /clr  
// C3450 expected  
using namespace System;  
using namespace System::Security;  
using namespace System::Security::Permissions;  
  
public ref class MyClass {};  
  
class MyClass2 {};  
  
[attribute(AttributeTargets::All)]  
ref struct AtClass {  
   AtClass(Type ^) {}  
};  
  
[attribute(AttributeTargets::All)]  
ref struct AtClass2 {  
   AtClass2() {}  
};  
  
// Apply the AtClass and AtClass2 attributes to class B  
[AtClass(MyClass::typeid), AtClass2]     
[AttributeUsage(AttributeTargets::All)]  
// Delete the following line to resolve.  
ref class B {};  
// Uncomment the following line to resolve.  
// ref class B : Attribute {};  
```