---
title: Оператор выражения | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- statements [C++], expression
- expression statements
ms.assetid: 547d7f7a-58be-4ffc-a4b3-d64c7ae7538c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 60879ca8792e3259a69b7a9a3de6cd83dce0d6d7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
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