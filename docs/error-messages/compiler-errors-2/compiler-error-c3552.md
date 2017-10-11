---
title: "Ошибка компилятора C3552 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3552
dev_langs:
- C++
helpviewer_keywords:
- C3552
ms.assetid: 83401524-1bf1-44c0-8aca-a6eb35c4224c
caps.latest.revision: 4
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 54526c39a928cc534ba815ef8fda802db85f4020
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3552"></a>Ошибка компилятора C3552
"имя_типа": тип возвращаемого значения с поздним заданием не может содержать "auto"  
  
 Если вы используете ключевое слово `auto` для типа возвращаемого значения функции, необходимо использовать тип возвращаемого значения с поздним заданием. Однако нельзя использовать другое ключевое слово `auto` для указания типа возвращаемого значения с поздним заданием. Например, представленный ниже фрагмент кода приводит к возникновению ошибки C3552.  
  
 `auto myFunction->auto; // C3552`
