---
title: "Ошибка компилятора C3050 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3050
dev_langs: C++
helpviewer_keywords: C3050
ms.assetid: ee090a0b-29cc-4215-a2f9-d82af79b8e82
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7754f04b271667165e5702e95491006bf82e61a1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3050"></a>Ошибка компилятора C3050
"тип1": класс ref не может наследовать от "тип1"  
  
 `System::ValueType` не может быть базовым классом для ссылочного типа.  
  
 В следующем примере возникает ошибка C3050.  
  
```  
// C3050.cpp  
// compile with: /clr /LD  
ref struct X : System::ValueType {};   // C3050  
ref struct Y {};   // OK  
```