---
title: "Атрибуты (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4438e03c-4de3-433d-abcc-31aa863bc0e0
caps.latest.revision: 8
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 8
---
# Атрибуты (C++/CX)
Атрибут представляет собой особый тип класса ссылки, который может в квадратных скобках указываться перед типами и методами [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)], чтобы задавать определенное поведение при создании метаданных. Некоторые предопределенные атрибуты, например [Windows::Foundation::Metadata::WebHostHidden](http://msdn.microsoft.com/library/windows/apps/windows.foundation.metadata.webhosthiddenattribute.aspx), обычно используются в коде [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]. В этом примере показано, как атрибут применяется к классу.  
  
 [!code-cpp[cx_attributes#01](../snippets/cpp/VS_Snippets_Misc/cx_attributes/cpp/class1.h#01)]  
  
## Настраиваемые атрибуты  
 Также можно определять настраиваемые атрибуты. Настраиваемые атрибуты должны соответствовать следующим правилам [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]:  
  
-   настраиваемые атрибуты могут содержать только открытые поля;  
  
-   поля настраиваемого атрибута можно инициализировать при применении атрибута к классу;  
  
-   поле может относиться к одному из следующих типов:  
  
    -   int32 \(int\)  
  
    -   uint32 \(unsigned int\)  
  
    -   bool  
  
    -   Platform::String^  
  
    -   Windows::Foundation::HResult  
  
    -   Platform::Type^  
  
    -   public enum class \(включая перечисления, определяемые пользователем\).  
  
 В следующем примере показано, как определить настраиваемый атрибут, а затем инициализировать его при использовании.  
  
 [!code-cpp[cx_attributes#02](../snippets/cpp/VS_Snippets_Misc/cx_attributes/cpp/class1.h#02)]  
  
## См. также  
 [Система типов \(C\+\+\/CX\)](../cppcx/type-system-c-cx.md)   
 [Справочник по языку C\+\+](../cppcx/visual-c-language-reference-c-cx.md)   
 [Справочник по пространствам имен](../cppcx/namespaces-reference-c-cx.md)