---
title: "Оператор выражения | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- statements [C++], expression
- expression statements
ms.assetid: 547d7f7a-58be-4ffc-a4b3-d64c7ae7538c
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: b48bf6d0dfd1c1ce29d1d116a77d3445bd5e1e30
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="expression-statement"></a>Оператор выражений
Операторы выражений обеспечивают вычисление выражений. В результате выполнения оператора выражения ни передачи управления, ни итерации не происходит.  
  
 Синтаксис оператора выражения простой:  
  
## <a name="syntax"></a>Синтаксис  
  
```  
[expression ] ;  
```  
  
## <a name="remarks"></a>Примечания  
 Вычисление всех выражений в операторе выражения и учет всех побочных эффектов осуществляются до выполнения следующего оператора. Самые распространенные операторы выражений — присваивания и вызовы функций.  Поскольку выражение не является обязательным, только точку с запятой считается пустым оператором выражения, называются [null](../cpp/null-statement.md) инструкции.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения об операторах в C++](../cpp/overview-of-cpp-statements.md)
