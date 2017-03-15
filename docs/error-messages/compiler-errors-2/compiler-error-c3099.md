---
title: "Compiler Error C3099 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3099"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3099"
ms.assetid: b3dded0f-76c9-42c1-991b-532eb8619661
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compiler Error C3099
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

keyword: используйте \[System::AttributeUsageAttribute\] для управляемых атрибутов; используйте \[Windows::Foundation::Metadata::AttributeUsageAttribute\] для атрибутов WinRT  
  
 Используйте <xref:System.AttributeUsageAttribute> для объявления атрибутов **\/clr**.  Используйте `Windows::Foundation::Metadata::AttributeUsageAttribute` для объявления атрибутов среды выполнения Windows.  
  
 Подробнее об атрибутах  \/CLR см. в разделе [Пользовательские атрибуты](../../windows/user-defined-attributes-cpp-component-extensions.md).  Описание атрибутов, поддерживаемых в среде выполнения Windows, см. в разделе [Пространство имен Windows.Foundation.Metadata](http://msdn.microsoft.com/library/windows/apps/windows.foundation.metadata.aspx)  
  
## Пример  
 В следующем примере показано возникновение ошибки C3099 и приводятся сведения по ее устранению.  
  
```  
// C3099.cpp  
// compile with: /clr /c  
using namespace System;  
[usage(10)]   // C3099  
// try the following line instead  
// [AttributeUsageAttribute(AttributeTargets::All)]  
ref class A : Attribute {};  
```