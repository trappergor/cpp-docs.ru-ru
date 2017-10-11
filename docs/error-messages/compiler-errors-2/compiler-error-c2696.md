---
title: "Ошибка компилятора C2696 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2696
dev_langs:
- C++
helpviewer_keywords:
- C2696
ms.assetid: 6c6eb7df-1230-4346-9a73-abf14c20785d
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 70ccaf34a0191f0bd69c95d2cb110f6e6542a6d1
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2696"></a>Ошибка компилятора C2696
Не удается создать временный объект управляемого типа «тип»  
  
Ссылки на `const` в неуправляемой программе при компиляции вызов конструктора и создание временного объекта в стеке. Тем не менее управляемый класс никогда не могут создаваться в стеке.  
  
C2696 доступен только с помощью параметра компилятора устаревшие **/CLR: oldSyntax**.  

