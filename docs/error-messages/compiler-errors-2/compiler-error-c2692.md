---
title: "Ошибка компилятора C2692 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2692
dev_langs:
- C++
helpviewer_keywords:
- C2692
ms.assetid: 02ade3b4-b757-448b-b065-d7d71bc3f441
caps.latest.revision: 12
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
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: cf1396ee49f433bae65e91b618d6afc246e43f9a
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2692"></a>Ошибка компилятора C2692
«имя функции»: компилятора C необходимы полные прототипы функций "/ clr" параметр  
  
 При компиляции для .NET управляемый код, компилятору C необходимы объявления функций ANSI. Кроме того, если функция не принимает параметров, его необходимо явно объявить `void` типа параметра.
