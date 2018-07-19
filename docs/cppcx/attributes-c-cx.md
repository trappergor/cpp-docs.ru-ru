---
title: Атрибуты (C + +/ CX) | Документы Microsoft
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: 4438e03c-4de3-433d-abcc-31aa863bc0e0
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 627e89c844b97637897c9b5eb6c1cc7e32081fd6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33086848"
---
# <a name="attributes-ccx"></a>Атрибуты (C++/CX)
Атрибут — это специальный класс ссылки, который может указываться в квадратных скобках типов среды выполнения Windows и методы, чтобы задавать определенное поведение при создании метаданных. Несколько предопределенных атрибутов — например, [Windows::Foundation::Metadata::WebHostHidden](http://msdn.microsoft.com/library/windows/apps/windows.foundation.metadata.webhosthiddenattribute.aspx)— обычно используются в C + +/ CX кода. В этом примере показано, как атрибут применяется к классу.  
  
 [!code-cpp[cx_attributes#01](../cppcx/codesnippet/CPP/cx_attributes/class1.h#01)]  
  
## <a name="custom-attributes"></a>Настраиваемые атрибуты  
 Также можно определять настраиваемые атрибуты. Настраиваемые атрибуты должны соответствовать следующим правилам среды выполнения Windows:  
  
-   настраиваемые атрибуты могут содержать только открытые поля;  
  
-   поля настраиваемого атрибута можно инициализировать при применении атрибута к классу;  
  
-   поле может относиться к одному из следующих типов:  
  
    -   int32 (int)  
  
    -   uint32 (unsigned int)  
  
    -   bool  
  
    -   Platform::String^  
  
    -   Windows::Foundation::HResult  
  
    -   Platform::Type^  
  
    -   public enum class (включая перечисления, определяемые пользователем).  
  
 В следующем примере показано, как определить настраиваемый атрибут, а затем инициализировать его при использовании.  
  
 [!code-cpp[cx_attributes#02](../cppcx/codesnippet/CPP/cx_attributes/class1.h#02)]  
  
## <a name="see-also"></a>См. также  
 [Система типов (C++/CX)](../cppcx/type-system-c-cx.md)   
 [Справочник по языку Visual C++](../cppcx/visual-c-language-reference-c-cx.md)   
 [Справочник по пространствам имен](../cppcx/namespaces-reference-c-cx.md)