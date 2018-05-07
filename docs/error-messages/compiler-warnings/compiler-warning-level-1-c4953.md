---
title: Предупреждение (уровень 1) C4953 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4953
dev_langs:
- C++
helpviewer_keywords:
- C4953
ms.assetid: 3c4f6ac6-3976-41ab-8a27-3c41d7472ea7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0af5a16ebbf7851eceb2f2cd355f953b14c4bd38
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4953"></a>Предупреждение компилятора (уровень 1) C4953
"функция": выполнено редактирование встроенного кода после сбора данных профилирования, данные профилирования не используются  
  
 При использовании параметра [/LTCG:PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md)компилятор обнаружил входной модуль, который был перекомпилирован после `/LTCG:PGINSTRUMENT` , имеет измененную функцию (***функция***) и в котором выполняется тест, определивший функцию для встраивания. Однако после перекомпиляции модуля функция больше не является кандидатом для встраивания.  
  
 Это предупреждение носит информационный характер. Чтобы решить проблему, связанную с этим предупреждением, запустите `/LTCG:PGINSTRUMENT`, повторите все тестовые запуски и запустите `/LTCG:PGOPTIMIZE`.  
  
 Вместо этого предупреждения будет ошибка, если использовался параметр `/LTCG:PGOPTIMIZE` .