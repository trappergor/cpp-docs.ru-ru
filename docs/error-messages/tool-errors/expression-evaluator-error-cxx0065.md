---
title: "Ошибка вычислителя выражений CXX0065 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- CXX0065
dev_langs:
- C++
helpviewer_keywords:
- CAN0065
- CXX0065
ms.assetid: aac68f87-0b90-4c19-afa6-1c587625a5fd
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: ff7093ee69dea3f39a37110bdc8076d1dc0e5cbe
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="expression-evaluator-error-cxx0065"></a>Ошибка вычислителя выражений CXX0065
для переменной требуется фрейм стека  
  
 Выражение содержит переменную, которая существует в текущей области, но еще не создан.  
  
 Это ошибка может возникать, если заход в прологе функции, но еще не Настройка кадр стека для функции, или если вы шаг с заходом в код выхода для функции.  
  
 Пошаговое выполнение кода пролога, пока Настройка кадр стека перед вычислением выражения.  
  
 Эта ошибка идентична ошибке CAN0065.
