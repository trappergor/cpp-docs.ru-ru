---
title: "Предупреждение (уровень 2) C4275 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4275
dev_langs:
- C++
helpviewer_keywords:
- C4275
ms.assetid: 18de967a-0a44-4dbc-a2e8-fc4c067ba909
caps.latest.revision: 14
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 3f69f0c3176d2fbe19e11ce08c071691a72d858d
ms.openlocfilehash: 873a96d4595b75ff6b9567500723c32d7ba5bd2b
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-2-c4275"></a>Предупреждение компилятора (уровень 2) C4275
не-интерфейс DLL classkey «идентификатор» используется в качестве основы для интерфейса DLL classkey «идентификатор»  
  
 Экспортированный класс является производным от класса, который не был экспортирован.  
  
 Чтобы свести к минимуму возможность повреждения данных при экспорте класса с [__declspec(dllexport)](../../cpp/dllexport-dllimport.md), убедитесь, что:  
  
-   Все статистические данные доступны посредством функций, экспортированных из библиотеки DLL.  
  
-   Без встроенных методов этого класса можно изменить статистические данные.  
  
-   Без встроенных методов класса использовать функции CRT или другие функции библиотек используют статистические данные.  
  
-   Нет класса встроенных функций используйте функции CRT или другие функции библиотек, где, например, доступ статических данных.  
  
-   Не один из методов класса (независимо от встраивания) можно использовать типы, где экземпляров в EXE и DLL присутствует отличие статистических данных.  
  
 Экспортирование классов, определяя, библиотеки DLL, которая определяет класс с виртуальными функциями и функций, которые можно использовать для создания и удаления объектов типа, можно предотвратить.  Можно просто вызвать виртуальные функции типа.  
  
 Дополнительные сведения об экспорте шаблонов см. в разделе [http://support.microsoft.com/default.aspx?scid=KB; EN-US;&16895;8](http://support.microsoft.com/default.aspx?scid=KB;EN-US;168958).  
  
 C4275 может быть проигнорирована в Visual C++ при наследовании от типа из стандартной библиотеки C++, компиляции отладочного выпуска (**/MTd**), где сообщение об ошибке компилятора ссылается на _Container_base.  
  
```  
// C4275.cpp  
// compile with: /EHsc /MTd /W2 /c  
#include <vector>  
using namespace std;  
class Node;  
class __declspec(dllimport) VecWrapper : vector<Node *> {};   // C4275  
```
