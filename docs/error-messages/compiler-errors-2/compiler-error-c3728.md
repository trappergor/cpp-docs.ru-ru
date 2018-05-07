---
title: Ошибка компилятора C3728 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3728
dev_langs:
- C++
helpviewer_keywords:
- C3728
ms.assetid: 6b510cb1-887f-4fcd-9a1f-3bb720417ed1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bae204db616db9e7d7e04cfd62d53374b0793aa9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3728"></a>Ошибка компилятора C3728
«событие»: событие не имеет метода raise  
  
 Метаданные, созданные с помощью другого языка, таких как C#, которые не позволяет создавать событие вне класса, в котором он был определен, была включена в [#using](../../preprocessor/hash-using-directive-cpp.md) директивы и программы Visual C++ с помощью программирования вызов событий.  
  
 Чтобы вызвать событие в программе, разработанное на языке, например C#, необходимо также определить открытый метод, который вызывает событие класса, содержащего событие.