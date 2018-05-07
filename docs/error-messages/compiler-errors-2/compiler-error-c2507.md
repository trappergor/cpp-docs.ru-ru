---
title: Ошибка компилятора C2507 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2507
dev_langs:
- C++
helpviewer_keywords:
- C2507
ms.assetid: f102aff5-de7d-4c3f-9cac-2ddf9ce02b14
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 82bd4fb028712093a44ada4ae58e97c2fbcf7eed
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2507"></a>Ошибка компилятора C2507
«Идентификатор»: слишком много виртуальных модификаторов для базового класса  
  
 Класс или структура была объявлена как `virtual` более одного раза. Только один `virtual` модификатор может использоваться для каждого класса в списке базовых классов.  
  
 Следующий пример приводит к возникновению ошибки C2507:  
  
```  
// C2507.cpp  
// compile with: /c  
class A {};  
class B : virtual virtual public A {};   // C2507  
class C : virtual public A {};   // OK  
```