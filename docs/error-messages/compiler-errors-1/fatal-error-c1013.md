---
title: "Неустранимая ошибка C1013 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C1013
dev_langs:
- C++
helpviewer_keywords:
- C1013
ms.assetid: 5514a679-efe7-4055-bdd3-5693ca0c332f
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
ms.openlocfilehash: 66e993458cfff9654ab05353758d7c7e9a5f6b10
ms.lasthandoff: 04/12/2017

---
# <a name="fatal-error-c1013"></a>Неустранимая ошибка C1013
ограничение компилятора: слишком много открывающих круглых скобок  
  
 Выражение содержит слишком много уровней круглых скобок в одном выражении. Упростите выражение или разбейте его на несколько инструкций.  
  
 До Visual C++ 6.0 с пакетом обновления 3 в одном выражении могло быть не более 59 вложенных круглых скобок. В настоящее время ограничение на количество круглых скобок увеличено до 256.
