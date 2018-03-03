---
title: "Ошибка компилятора C3161 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3161
dev_langs:
- C++
helpviewer_keywords:
- C3161
ms.assetid: 1fe2be85-a343-487b-8476-bf9e257eb29d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c0cdbbd9364435ebcfad114331b6ba7289cb8010
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3161"></a>Ошибка компилятора C3161
«интерфейс»: вложенный класс, структура, объединение или интерфейс в интерфейсе недопустимы; недопустимо вложение интерфейса в класс, структура или объединение  
  
 [__Interface](../../cpp/interface.md) может появиться только в глобальной области видимости в пределах пространства имен. Класс, структура или объединение не может присутствовать в интерфейсе.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C3161.  
  
```  
// C3161.cpp  
// compile with: /c  
__interface X {  
   __interface Y {};   // C3161 A nested interface  
};  
```