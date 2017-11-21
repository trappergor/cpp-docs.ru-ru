---
title: "Предупреждение (уровень 1) C4612 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4612
dev_langs: C++
helpviewer_keywords: C4612
ms.assetid: 21ac02b2-51cd-4aff-9b70-d543511d5962
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1a2d5ddc76271df594c2bd5b2ae1707933510338
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4612"></a>Предупреждение компилятора (уровень 1) C4612
ошибка в имени включаемого файла  
  
 Это предупреждение возникает с **#pragma include_alias** , когда имя файла указано неправильно или отсутствует.  
  
 Аргументы для оператора **#pragma include_alias** могут использовать форму с кавычками (**"***имя_файла***"**) или форму с угловыми скобками (**\<***имя_файла***>**), но оба аргументы должны использовать одну и ту же форму.  
  
## <a name="example"></a>Пример  
  
```  
// C4612.cpp  
// compile with: /W1 /LD  
#pragma include_alias("StandardIO", <stdio.h>) // C4612  
```