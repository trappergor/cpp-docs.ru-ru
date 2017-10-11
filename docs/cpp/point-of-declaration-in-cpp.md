---
title: "Точка объявления в C++ | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- point of declaration
ms.assetid: 92ea8707-80cb-497c-b479-f907b8401859
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 77f66182052cc2a031b7f1f8db8018f49b36801d
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="point-of-declaration-in-c"></a>Точка объявления в C++
Имя считается объявленным сразу после его декларатора, но перед его (необязательным) инициализатором. (Дополнительные сведения о деклараторах см. в разделе [объявления и определения](declarations-and-definitions-cpp.md).)  
  
 Рассмотрим следующий пример.  
  
```  
// point_of_declaration1.cpp  
// compile with: /W1   
double dVar = 7.0;  
int main()  
{  
   double dVar = dVar;   // C4700  
}  
```  
  
 Если точка объявления располагалась *после* инициализации, то локальная `dVar` инициализировалась 7,0 — значением глобальной переменной `dVar`. Поскольку это не так, `dVar` инициализируется неопределенным значением.  
  
## <a name="see-also"></a>См. также  
 [Область](../cpp/scope-visual-cpp.md)
