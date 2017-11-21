---
title: "Предупреждение (уровень 2) C4275 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4275
dev_langs: C++
helpviewer_keywords: C4275
ms.assetid: 18de967a-0a44-4dbc-a2e8-fc4c067ba909
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 46204fb7b87c556756db3debbe9bdc9031c9c343
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-2-c4275"></a>Предупреждение компилятора (уровень 2) C4275
не - интерфейс DLL classkey «идентификатор» используется в качестве базы для classkey интерфейс DLL «идентификатор»  
  
 Экспортированный класс является производным от класса, который не был экспортирован.  
  
 Чтобы свести к минимуму вероятность повреждения данных при экспорте класса с [__declspec(dllexport)](../../cpp/dllexport-dllimport.md), убедитесь, что:  
  
-   Все статические данные осуществляется с помощью функций, экспортированных из библиотеки DLL.  
  
-   Ни один встроенных методов этого класса можно изменить статические данные.  
  
-   Функции CRT, которые использовать ни встроенных методов класса или других функций библиотеки статических данных.  
  
-   Нет класса встроенных функций используйте функции CRT, или другие функции библиотеки, where, например, доступ статических данных.  
  
-   Нет один из методов класса (независимо от встраивания) можно использовать типы, где экземпляров в EXE и DLL присутствует отличие статистических данных.  
  
 Экспортирование классов, определяя, которые библиотеку DLL, которая определяет класс с виртуальными функциями и функций, которые можно использовать для создания и удаления объектов типа, можно предотвратить.  Можно просто вызывать виртуальные функции в типе.  
  
 Дополнительные сведения об экспорте шаблонов см. в разделе [http://support.microsoft.com/default.aspx?scid=KB; EN-US; 168958](http://support.microsoft.com/default.aspx?scid=KB;EN-US;168958).  
  
 Можно игнорировать C4275 в Visual C++ при наследовании от типа из стандартной библиотеки C++, компиляция отладочного выпуска (**/MTd**), где сообщение об ошибке компилятора ссылается на _Container_base.  
  
```  
// C4275.cpp  
// compile with: /EHsc /MTd /W2 /c  
#include <vector>  
using namespace std;  
class Node;  
class __declspec(dllimport) VecWrapper : vector<Node *> {};   // C4275  
```