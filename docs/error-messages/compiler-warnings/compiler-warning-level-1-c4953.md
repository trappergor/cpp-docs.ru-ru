---
title: "Компилятор C4953 предупреждение (уровень 1) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4953
dev_langs:
- C++
helpviewer_keywords:
- C4953
ms.assetid: 3c4f6ac6-3976-41ab-8a27-3c41d7472ea7
caps.latest.revision: 8
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: be8e32bd07da47d79e974d979eb19466c5b19416
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4953"></a>Предупреждение компилятора (уровень 1) C4953
"функция": выполнено редактирование встроенного кода после сбора данных профилирования, данные профилирования не используются  
  
 При использовании [/LTCG: PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md), компилятор обнаружил модуль ввода, который был перекомпилирован после `/LTCG:PGINSTRUMENT` и содержит функцию (***функция***) был изменен, и где выполняется тест считается кандидатом на функции встраивания. Однако после перекомпиляции модуля функция больше не является кандидатом для встраивания.  
  
 Это предупреждение носит информационный характер. Чтобы решить проблему, связанную с этим предупреждением, запустите `/LTCG:PGINSTRUMENT`, повторите все тестовые запуски и запустите `/LTCG:PGOPTIMIZE`.  
  
 Вместо этого предупреждения будет ошибка, если использовался параметр `/LTCG:PGOPTIMIZE` .
