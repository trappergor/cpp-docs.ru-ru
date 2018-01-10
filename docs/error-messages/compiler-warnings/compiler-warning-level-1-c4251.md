---
title: "Предупреждение (уровень 1) C4251 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4251
dev_langs: C++
helpviewer_keywords: C4251
ms.assetid: a9992038-f0c2-4fc4-a9be-4509442cbc1e
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5b220913d97755547a9cb35fe326f9fb9a06e40a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4251"></a>Предупреждение компилятора (уровень 1) C4251
«Идентификатор»: класс «тип» должен иметь интерфейс dll для использования клиентами класса «тип2»  
  
 Чтобы свести к минимуму вероятность повреждения данных при экспорте класса с [__declspec(dllexport)](../../cpp/dllexport-dllimport.md), убедитесь, что:  
  
-   Все статические данные — доступ с помощью функций, экспортированных из библиотеки DLL.  
  
-   Ни один встроенных методов этого класса можно изменить статические данные.  
  
-   Функции CRT, которые использовать ни встроенных методов класса или других функций библиотеки статические данные (см. [потенциальные ошибки передачи CRT объекты через границы DLL](../../c-runtime-library/potential-errors-passing-crt-objects-across-dll-boundaries.md) для получения дополнительной информации).  
  
-   Нет один из методов класса (независимо от встраивания) можно использовать типы, где экземпляров в EXE и DLL присутствует отличие статистических данных.  
  
 Экспортирование классов, определяя, которые библиотеку DLL, которая определяет класс с виртуальными функциями и функций, которые можно использовать для создания и удаления объектов типа, можно предотвратить.  Можно просто вызывать виртуальные функции в типе.  
  
 Дополнительные сведения об экспорте шаблонов см. в разделе [http://support.microsoft.com/default.aspx?scid=KB; EN-US; 168958](http://support.microsoft.com/default.aspx?scid=KB;EN-US;168958).  
  
 При наследовании от типа из стандартной библиотеки C++, компиляция отладочного выпуска можно игнорировать C4251 (**/MTd**), где сообщение об ошибке компилятора ссылается на _Container_base.  
  
```  
// C4251.cpp  
// compile with: /EHsc /MTd /W2 /c  
#include <vector>  
using namespace std;  
class Node;  
class __declspec(dllimport) VecWrapper : vector<Node *> {};   // C4251  
```