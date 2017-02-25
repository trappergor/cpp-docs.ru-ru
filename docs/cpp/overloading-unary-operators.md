---
title: "Перегрузка унарных операторов | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "операторы увеличения, перегруженные"
  - "операторы [C++], унарные"
  - "plus - оператор"
  - "перезагрузка оператора разыменования указателя"
  - "переопределяемые унарные операторы"
  - "унарные операторы"
  - "унарные операторы, minus"
  - "унарные операторы, plus"
ms.assetid: 7683ef08-42a4-4283-928f-d3dd4f3ab4c0
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Перегрузка унарных операторов
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Перегрузке могут быть подвергнуты следующие унарные операторы.  
  
1.  `!` \([логическое НЕ](../cpp/logical-negation-operator-exclpt.md)\)  
  
2.  `&` \([взятие адреса](../cpp/address-of-operator-amp.md)\)  
  
3.  `~` \([дополнение до единицы](../cpp/one-s-complement-operator-tilde.md)\)  
  
4.  `*` \([разыменование указателя](../cpp/indirection-operator-star.md)\)  
  
5.  `+` \([унарный плюс](../cpp/additive-operators-plus-and.md)\)  
  
6.  `-` \([унарное отрицание](../cpp/additive-operators-plus-and.md)\)  
  
7.  `++` \([инкремент](../Topic/Prefix%20Increment%20and%20Decrement%20Operators:%20++%20and%20--.md)\)  
  
8.  `--` \([декремент](../Topic/Prefix%20Increment%20and%20Decrement%20Operators:%20++%20and%20--.md)\)  
  
9. операторы преобразования  
  
 Постфиксные операторы приращения и декремента \(`++` и **––**\) рассматриваются отдельно в разделе [Приращение и декремент](../Topic/Increment%20and%20Decrement%20Operator%20Overloading%20\(C++\).md).  
  
 Операторы преобразования также обсуждаются в отдельном разделе \(см. раздел [Преобразования](../cpp/user-defined-type-conversions-cpp.md)\).  
  
 Следующие правила распространяются на все остальные унарные операторы.  Чтобы объявить функцию унарного оператора как нестатический член, необходимо объявить ее в форме  
  
 `ret-type operator` `op` `()`  
  
 где `ret-type` — возвращаемый тип, а `op` — один из операторов, перечисленных в предыдущей таблице.  
  
 Чтобы объявить функцию унарного оператора как глобальную функцию, необходимо объявить ее в форме  
  
 `ret-type operator` `op` \(`arg` \)  
  
 где `ret-type` и `op` соответствуют описанию для функций\-членов операторов, а `arg` — аргумент типа класса, с которым необходимо выполнить операцию.  
  
> [!NOTE]
>  Не существует ограничения на возвращаемые типы унарных операторов.  Например, логическому НЕ \(`!`\) имеет смысл возвращать целочисленное значение, однако это не реализовано принудительно.  
  
## См. также  
 [Перегрузка операторов](../cpp/operator-overloading.md)