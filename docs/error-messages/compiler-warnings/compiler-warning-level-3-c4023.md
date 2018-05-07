---
title: Предупреждение (уровень 3) C4023 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4023
dev_langs:
- C++
helpviewer_keywords:
- C4023
ms.assetid: 615d5374-d7c1-42eb-acfd-917c053270c8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 213d72e39575b447787c3e0ead7910baedc8e815
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-3-c4023"></a>Предупреждение компилятора (уровень 3) C4023
"символ": относительный указатель передан в функцию без прототипа: номер параметра  
  
 Передача относительного указателя в функцию без прототипа нормализует указатель с непредвиденными результатами.  
  
 Чтобы устранить это предупреждение, используйте функции прототипа, которые передаются относительными указателями.