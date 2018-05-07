---
title: Предупреждение (уровень 1) C4251 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4251
dev_langs:
- C++
helpviewer_keywords:
- C4251
ms.assetid: a9992038-f0c2-4fc4-a9be-4509442cbc1e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 366d66a38685e75e47d8921f9ebd525b334ced7e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4251"></a>Предупреждение компилятора (уровень 1) C4251
«Идентификатор»: класс «тип» должен иметь интерфейс dll для использования клиентами класса «тип2»  
  
 Чтобы свести к минимуму вероятность повреждения данных при экспорте класса с [__declspec(dllexport)](../../cpp/dllexport-dllimport.md), убедитесь, что:  
  
-   Все статические данные — доступ с помощью функций, экспортированных из библиотеки DLL.  
  
-   Ни один встроенных методов этого класса можно изменить статические данные.  
  
-   Функции CRT, которые использовать ни встроенных методов класса или других функций библиотеки статические данные (см. [потенциальные ошибки передачи CRT объекты через границы DLL](../../c-runtime-library/potential-errors-passing-crt-objects-across-dll-boundaries.md) для получения дополнительной информации).  
  
-   Нет один из методов класса (независимо от встраивания) можно использовать типы, где экземпляров в EXE и DLL присутствует отличие статистических данных.  
  
 Экспортирование классов, определяя, которые библиотеку DLL, которая определяет класс с виртуальными функциями и функций, которые можно использовать для создания и удаления объектов типа, можно предотвратить.  Можно просто вызывать виртуальные функции в типе.  
  
 Дополнительные сведения об экспорте шаблонов см. в разделе [ http://support.microsoft.com/default.aspx?scid=KB; EN-US; 168958](http://support.microsoft.com/default.aspx?scid=KB;EN-US;168958).  
  
 При наследовании от типа из стандартной библиотеки C++, компиляция отладочного выпуска можно игнорировать C4251 (**/MTd**), где сообщение об ошибке компилятора ссылается на _Container_base.  
  
```  
// C4251.cpp  
// compile with: /EHsc /MTd /W2 /c  
#include <vector>  
using namespace std;  
class Node;  
class __declspec(dllimport) VecWrapper : vector<Node *> {};   // C4251  
```