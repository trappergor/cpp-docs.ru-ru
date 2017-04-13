---
title: "Предупреждение (уровень 1) C4612 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4612
dev_langs:
- C++
helpviewer_keywords:
- C4612
ms.assetid: 21ac02b2-51cd-4aff-9b70-d543511d5962
caps.latest.revision: 6
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
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: ede7b643c5be50f430859f2716e542560d6b04c5
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-1-c4612"></a>Предупреждение компилятора (уровень 1) C4612
ошибка в имени включаемого файла  
  
 Это предупреждение возникает с **#pragma include_alias** , когда имя файла указано неправильно или отсутствует.  
  
 Аргументы для **#pragma include_alias** инструкции можно использовать с кавычками (**»***filename***»**) или форму с угловыми скобками (**\<***filename***>**), но оба должны использовать ту же форму.  
  
## <a name="example"></a>Пример  
  
```  
// C4612.cpp  
// compile with: /W1 /LD  
#pragma include_alias("StandardIO", <stdio.h>) // C4612  
```
