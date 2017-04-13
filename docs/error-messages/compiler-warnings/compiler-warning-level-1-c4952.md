---
title: "Предупреждение (уровень 1) C4952 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4952
dev_langs:
- C++
helpviewer_keywords:
- C4952
ms.assetid: 593324f0-5cfe-42fb-b221-2f71308765dd
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
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: fa48ab2f0e7a2a9d7675af5d2e88aa56b100f022
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-1-c4952"></a>Предупреждение компилятора (уровень 1) C4952
"функция": данные профилирования не найдены в базе данных программы "pgd-файл"  
  
 При использовании [/LTCG: PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md), компилятор обнаружил модуль ввода, который был перекомпилирован после `/LTCG:PGINSTRUMENT` и имеет новую функцию (***функция***) отсутствует.  
  
 Это предупреждение носит информационный характер. Чтобы решить проблему, связанную с этим предупреждением, запустите `/LTCG:PGINSTRUMENT`, повторите все тестовые запуски и запустите `/LTCG:PGOPTIMIZE`.  
  
 Вместо этого предупреждения будет ошибка, если использовался параметр `/LTCG:PGOPTIMIZE` .
