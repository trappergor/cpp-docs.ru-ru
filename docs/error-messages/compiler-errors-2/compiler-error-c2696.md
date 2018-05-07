---
title: Ошибка компилятора C2696 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2696
dev_langs:
- C++
helpviewer_keywords:
- C2696
ms.assetid: 6c6eb7df-1230-4346-9a73-abf14c20785d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 65ccdd6d2c8c34c360811b80d5a93abe76f5ef8e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2696"></a>Ошибка компилятора C2696
Не удается создать временный объект управляемого типа «тип»  
  
Ссылки на `const` в неуправляемой программе при компиляции вызов конструктора и создание временного объекта в стеке. Тем не менее управляемый класс никогда не могут создаваться в стеке.  
  
C2696 доступен только с помощью параметра компилятора устаревшие **/CLR: oldSyntax**.  
