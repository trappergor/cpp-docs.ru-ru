---
title: Атрибуты (C + +/ CX) | Документация Майкрософт
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: 4438e03c-4de3-433d-abcc-31aa863bc0e0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7db8d6c527842cd3784623002fba001a4174c1fc
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42601142"
---
# <a name="attributes-ccx"></a>Атрибуты (C++/CX)
Атрибут — это специальный класс ссылки, могут быть использованы в квадратных скобках типов среды выполнения Windows и методы, чтобы задавать определенное поведение при создании метаданных. Несколько предопределенных атрибутов — например, [Windows::Foundation::Metadata::WebHostHidden](http://msdn.microsoft.com/library/windows/apps/windows.foundation.metadata.webhosthiddenattribute.aspx)— обычно используются в C + +/ CX кода. В этом примере показано, как атрибут применяется к классу.  
  
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