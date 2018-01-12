---
title: "Ошибка компилятора C3291 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3291
dev_langs: C++
helpviewer_keywords: C3291
ms.assetid: ed2e9f89-8dbc-4387-bc26-cc955e840858
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e129aca0900624e8b1298ee97754bdfa67ea5a37
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3291"></a>Ошибка компилятора C3291
default: не может быть именем тривиального свойства  
  
 Тривиальное свойство нельзя назвать `default` Дополнительные сведения см. в разделе [property](../../windows/property-cpp-component-extensions.md) .  
  
## <a name="example"></a>Пример  
 В следующем примере возникает ошибка C3291.  
  
```  
// C3291.cpp  
// compile with: /clr /c  
ref struct C {  
   property System::String ^ default;   // C3291  
   property System::String ^ Default;   // OK  
};  
```