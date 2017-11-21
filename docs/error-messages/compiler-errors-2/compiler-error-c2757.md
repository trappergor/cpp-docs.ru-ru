---
title: "Ошибка компилятора C2757 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2757
dev_langs: C++
helpviewer_keywords: C2757
ms.assetid: 421f102f-8a32-4d47-a109-811ddf2c909d
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e10d357679fc7a0d1a5e183bdc1eb95a7a597c00
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2757"></a>Ошибка компилятора C2757
«символ»: символ с таким именем уже существует и поэтому оно не может использоваться как имя пространства имен  
  
 Символ, используемый в текущей компиляции как идентификатор пространства имен уже используется в сборке, на которую указывает ссылка.  
  
 Следующий пример приводит к возникновению ошибки C2757:  
  
```  
// C2757a.cpp  
// compile with: /clr /LD  
public ref class Nes {};  
```  
  
 Затем:  
  
```  
// C2757b.cpp  
// compile with: /clr /c  
#using <C2757a.dll>  
  
namespace Nes {    // C2757  
// try the following line instead  
// namespace Nes2 {  
   public ref class X {};  
}  
```  
