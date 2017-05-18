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
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: ae268ae3c0d7857aa2c2cbafe9e158656f657f1a
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3552"></a>Ошибка компилятора C3552
"имя_типа": тип возвращаемого значения с поздним заданием не может содержать "auto"  
  
 Если вы используете ключевое слово `auto` для типа возвращаемого значения функции, необходимо использовать тип возвращаемого значения с поздним заданием. Однако нельзя использовать другое ключевое слово `auto` для указания типа возвращаемого значения с поздним заданием. Например, представленный ниже фрагмент кода приводит к возникновению ошибки C3552.  
  
 `auto myFunction->auto; // C3552`
