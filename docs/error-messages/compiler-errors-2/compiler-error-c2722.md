---
title: "Ошибка компилятора C2722 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2722
dev_langs:
- C++
helpviewer_keywords:
- C2722
ms.assetid: 4cc2c7fa-cb12-4bcf-9df1-6d627ef62973
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: c2db3d8ac30d51e04d425bd27e9d9d5c12e62931
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2722"></a>Ошибка компилятора C2722
":: оператор": недопустимое обозначение оператора; Используйте оператор «оператор»  
  
 `operator` Переопределяет оператор `::new` или `::delete`. `new` И `delete` операторы являются глобальными, поэтому оператор разрешения области действия (`::`) не имеет смысла. Удалить `::` оператор.
