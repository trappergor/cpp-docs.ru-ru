---
title: Ошибка компилятора C2834 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2834
dev_langs:
- C++
helpviewer_keywords:
- C2834
ms.assetid: 28f9f6eb-ab2a-4e64-aaaa-9d14f955de41
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4eb4fb992f9213c4a4b456f786fd8f81308cec12
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33244788"
---
# <a name="compiler-error-c2834"></a>Ошибка компилятора C2834
«оператор» должен иметь глобальное полное имя  
  
 `new` И `delete` операторы привязаны к классу, сохранились они или нет. Разрешение области не может использоваться для выбора версии `new` или `delete` от другого класса. Чтобы реализовать несколько форм `new` или `delete` оператор, создайте версию оператора с дополнительными формальными параметрами.