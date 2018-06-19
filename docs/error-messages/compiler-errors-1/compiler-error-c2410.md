---
title: Ошибка компилятора C2410 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2410
dev_langs:
- C++
helpviewer_keywords:
- C2410
ms.assetid: b69b2de1-56f3-4ebc-8913-04ac57ffe8a1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f9c2a2df0941130c4f2416806a05ce0378373eb4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33226452"
---
# <a name="compiler-error-c2410"></a>Ошибка компилятора C2410
«Идентификатор»: неоднозначное имя члена в «контекст»  
  
 Идентификатор является членом более чем одной структуры или объединения в этом контексте.  
  
 Используйте структуры или объединения спецификатор операнда, который вызвал ошибку. Спецификатор структуры или объединения является идентификатором типа `struct` или `union` ( `typedef` имени или переменной того же типа, что структуры или объединения на которые ссылаются). Описатель должен быть левым операндом первого оператора выбора члена (.) чтобы использовать операнд.