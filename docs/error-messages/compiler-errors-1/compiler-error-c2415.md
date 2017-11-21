---
title: "Ошибка компилятора C2415 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2415
dev_langs: C++
helpviewer_keywords: C2415
ms.assetid: f225c913-2bea-46b1-b096-3d358ac94a15
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 68666ba203897b43fb1658525e1f342bcb923c09
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2415"></a>Ошибка компилятора C2415
Недопустимый тип операнда  
  
 Код операции не использует операнды данного типа.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.  
  
1.  Код операции не поддерживает количество используемых операндов. Проверьте сборку с руководством по языку определить правильное число операндов.  
  
2.  Новый процесс поддерживает инструкции с новыми типами. Настройка [/arch (минимальная архитектура ЦП)](../../build/reference/arch-minimum-cpu-architecture.md) параметр, чтобы использовать более новый процессор.