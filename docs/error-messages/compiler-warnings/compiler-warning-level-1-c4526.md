---
title: Предупреждение (уровень 1) C4526 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4526
dev_langs:
- C++
helpviewer_keywords:
- C4526
ms.assetid: 490f8916-5fdc-4cad-b412-76c3382a5976
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c5a38d629d61e16b038701522d4bb27a4de7391d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4526"></a>Предупреждение компилятора (уровень 1) C4526
«функция»: статическая функция-член не может переопределить виртуальную функцию "виртуальный function'override игнорируются, виртуальная функция будет скрыта.  
  
 Статическая функция-член удовлетворяет критериям для переопределения виртуальной функции, вследствие чего функция-член как виртуальные, так и статические.  
  
 Следующий код вызывает ошибку C4526:  
  
```  
// C4526.cpp  
// compile with: /W1 /c  
// C4526 expected  
struct myStruct1 {  
   virtual void __stdcall func( int ) = 0;  
};  
  
struct myStruct2: public myStruct1 {  
   static void __stdcall func( int );  
};  
```  
  
 Ниже приведены возможные исправления.  
  
-   Если функция должна переопределить виртуальную функцию базового класса, удалите статический спецификатор.  
  
-   Если функция должна быть статической функцией-членом, переименовываете ее, чтобы это не противоречит виртуальная функция базового класса.