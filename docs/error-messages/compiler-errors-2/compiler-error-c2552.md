---
title: "Ошибка компилятора C2552 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2552
dev_langs:
- C++
helpviewer_keywords:
- C2552
ms.assetid: 0e0ab759-788a-4faf-9337-80d4b9e2e8c9
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c1a438d602c23d15a1196fe4d40a5cca98867828
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2552"></a>Ошибка компилятора C2552
"идентификатор": инициализация не агрегированных данных с помощью списка инициализации не допускается  
  
 Идентификатор агрегата был неверно инициализирован.  
  
 [Статистические выражения](../../c-language/initializing-aggregate-types.md) определяются как:  
  
-   Массивы  
  
-   классы, структуры и объединения, у которых нет:  
  
    -   Конструкторы  
  
    -   закрытых или защищенных членов;  
  
    -   базовых классов;  
  
    -   Виртуальные функции  
  
 Кроме того, в Visual C++ в агрегатах не допускаются типы данных, содержащие конструкторы.  
  
 Ниже приведены причины, из-за которых при попытке инициализации агрегата для типа может возникнуть ошибка C2552:  
  
-   Тип имеет один или несколько пользовательских конструкторов.  
  
-   Тип имеет один или несколько нестатических, закрытых данных-членов.  
  
-   Тип имеет одну или несколько виртуальных функций.  
  
-   Тип имеет базовый класс.  
  
-   Тип является классом ссылки или интерфейсом среды CLR.  
  
-   Тим включает массив нефиксированного размера (нулевой массив), элементы которого имеют деструкторы.  
  
 Следующий пример приводит к возникновению ошибки C2552:  
  
```  
// C2552.cpp  
// compile with: /clr  
#include <string>  
using namespace std;  
  
struct Pair_Incorrect {  
private:  
   string m_name;  
   double m_val;  
};  
  
struct Pair_Correct1 {  
public:  
   Pair_Correct1(string name, double val)  
      : m_name(name), m_val(val) {}  
  
private:  
   string m_name;  
   double m_val;  
};  
  
struct Pair_Correct2 {  
public:  
   string m_name;  
   double m_val;  
};  
  
int main() {  
   // To fix, add a constructor to this class and use it for   
   // initializing the data members, see Pair_Correct1 (below)  
   // or  
   // Do not have any private or protected non-static data members,   
   // see Pair_Correct2 (below).  Pair_Correct2 is not recommended in   
   // case your object model requires some non-static data members to   
   // be private or protected  
  
   string name("John");  
   Pair_Incorrect pair1 = { name, 0.0 };   // C2552  
  
   // initialize a CLR immutable value type that has a constructor  
   System::DateTime dt = {2001, 4, 12, 22, 16, 49, 844};   // C2552   
  
   Pair_Correct1 pair2( name, 0.0 );  
   Pair_Correct1 pair3 = Pair_Correct1( name, 0.0 );  
   Pair_Correct2 pair4 = { name, 0.0 };  
   System::DateTime dt2(2001, 4, 12, 22, 16, 49, 844);  
}  
```