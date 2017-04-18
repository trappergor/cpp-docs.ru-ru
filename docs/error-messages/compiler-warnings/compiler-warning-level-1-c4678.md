---
title: "Предупреждение компилятора (уровень 1) предупреждение C4678 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4678
dev_langs:
- C++
helpviewer_keywords:
- C4678
ms.assetid: 0c588f34-595d-4e5c-9470-8723fca2cc06
caps.latest.revision: 10
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
translationtype: Machine Translation
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: d35e60d60d194bc0ca68a116dc45b6d9864d9fe2
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4678"></a>Предупреждение компилятора (уровень 1) C4678
базовый класс "базовый_тип" менее доступен, чем "производный_тип"  
  
Открытый тип является производным от закрытого типа. Если экземпляр открытого типа создается в связанной сборке, то члены закрытого базового типа будут недоступны.  
  
Предупреждение C4678 доступен только с помощью параметра компилятора устаревшие **/CLR: oldSyntax**. Приводит к ошибке при использовании **/CLR**для базового класса, менее доступного, производный от него класс.  

