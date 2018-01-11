---
title: "Ошибка компилятора C3728 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3728
dev_langs: C++
helpviewer_keywords: C3728
ms.assetid: 6b510cb1-887f-4fcd-9a1f-3bb720417ed1
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d20a0772a38dadc5956e1d174a23ecb0a8593647
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3728"></a>Ошибка компилятора C3728
«событие»: событие не имеет метода raise  
  
 Метаданные, созданные с помощью другого языка, таких как C#, которые не позволяет создавать событие вне класса, в котором он был определен, была включена в [#using](../../preprocessor/hash-using-directive-cpp.md) директивы и программы Visual C++ с помощью программирования вызов событий.  
  
 Чтобы вызвать событие в программе, разработанное на языке, например C#, необходимо также определить открытый метод, который вызывает событие класса, содержащего событие.