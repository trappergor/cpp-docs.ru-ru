---
title: Точка объявления в C++ | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- point of declaration
ms.assetid: 92ea8707-80cb-497c-b479-f907b8401859
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 89f94cdee6be18436b3f39f840fb7880e5860adb
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/01/2018
ms.locfileid: "39409379"
---
# <a name="point-of-declaration-in-c"></a>Точка объявления в C++
Имя считается объявленным сразу после его декларатора, но перед его (необязательным) инициализатором. (Дополнительные сведения о деклараторах см. в разделе [объявления и определения](declarations-and-definitions-cpp.md).)  
  
 Рассмотрим следующий пример.  
  
```cpp 
// point_of_declaration1.cpp  
// compile with: /W1   
double dVar = 7.0;  
int main()  
{  
   double dVar = dVar;   // C4700  
}  
```  
  
 Если точка объявления располагалась *после* инициализацию, то локальная `dVar` инициализировалась 7,0 — значением глобальной переменной `dVar`. Поскольку это не так, `dVar` инициализируется неопределенным значением.  
  
## <a name="see-also"></a>См. также  
 [Область](../cpp/scope-visual-cpp.md)