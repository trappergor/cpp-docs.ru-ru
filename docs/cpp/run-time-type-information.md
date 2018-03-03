---
title: "Сведения о типах времени выполнения | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: 'index-page '
dev_langs:
- C++
helpviewer_keywords:
- RTTI compiler option
- run-time type information
- run time, type checking
- type information, run-time type checking
- run-time checks, type checking
ms.assetid: becbd0e5-0439-4c61-854f-8a74f7160c54
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0b0b0124a69a0110bda94055964fbcdb54e5a754
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="run-time-type-information"></a>Сведения о типах времени выполнения
Информация о типах времени выполнения (RTTI) — это механизм, позволяющий определить тип объекта во время выполнения программы. Функция RTTI была добавлена в язык C++, поскольку многие поставщики библиотек классов реализовывали ее самостоятельно. Это приводило к проблемам совместимости между библиотеками. Таким образом, стало очевидно, что необходима поддержка информации о типах времени выполнения на уровне языка.  
  
 Для ясности этот раздел о RTTI почти полностью посвящен указателям. Однако рассматриваемые понятия также применяются ко ссылкам.  
  
 Существует три основных элемента языка C++ для информации о типах времени выполнения.  
  
-   [Dynamic_cast](../cpp/dynamic-cast-operator.md) оператор.  
  
     Используется для преобразования полиморфных типов.  
  
-   [Typeid](../cpp/typeid-operator.md) оператор.  
  
     Используется для указания точного типа объекта.  
  
-   [Type_info](../cpp/type-info-class.md) класса.  
  
     Используется для хранения информации о типе, возвращенной оператором `typeid`.  
  
## <a name="see-also"></a>См. также  
 [Приведение](../cpp/casting.md)