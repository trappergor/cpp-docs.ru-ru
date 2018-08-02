---
title: Оператор выражения | Документация Майкрософт
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
ms.openlocfilehash: d94acdfff2fdea2cc35d0856940270ba82e131af
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/01/2018
ms.locfileid: "39405260"
---
# <a name="expression-statement"></a>Оператор выражений
Операторы выражений обеспечивают вычисление выражений. В результате выполнения оператора выражения ни передачи управления, ни итерации не происходит.  
  
 Синтаксис оператора выражения простой:  
  
## <a name="syntax"></a>Синтаксис  
  
```  
[expression ] ;  
```  
  
## <a name="remarks"></a>Примечания  
 Вычисление всех выражений в операторе выражения и учет всех побочных эффектов осуществляются до выполнения следующего оператора. Самые распространенные операторы выражений — присваивания и вызовы функций.  Поскольку выражение является необязательным, отдельная точка с запятой считается пустым оператором выражения, называются [null](../cpp/null-statement.md) инструкции.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения об операторах в C++](../cpp/overview-of-cpp-statements.md)