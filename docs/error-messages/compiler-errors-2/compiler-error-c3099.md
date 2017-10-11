---
title: "Ошибка компилятора C3099 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3099
dev_langs:
- C++
helpviewer_keywords:
- C3099
ms.assetid: b3dded0f-76c9-42c1-991b-532eb8619661
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: b0303ef909d6f18cb54c70bc64ab06d415e96da5
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3099"></a>Ошибка компилятора C3099
keyword: используйте [System::AttributeUsageAttribute] для управляемых атрибутов; используйте [Windows::Foundation::Metadata::AttributeUsageAttribute] для атрибутов WinRT  
  
 Используйте <xref:System.AttributeUsageAttribute> для объявления **/CLR** атрибуты. Используйте `Windows::Foundation::Metadata::AttributeUsageAttribute` для объявления атрибутов среды выполнения Windows.  
  
 Дополнительные сведения об атрибутах/CLR см. в разделе [определяемые пользователем атрибуты](../../windows/user-defined-attributes-cpp-component-extensions.md). Для атрибутов, поддерживаемых в среды выполнения Windows, в разделе [имен Windows.Foundation.Metadata](http://msdn.microsoft.com/library/windows/apps/windows.foundation.metadata.aspx)  
  
## <a name="example"></a>Пример  
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
