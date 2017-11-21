---
title: "Предупреждение (уровень 1) C4953 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4953
dev_langs: C++
helpviewer_keywords: C4953
ms.assetid: 3c4f6ac6-3976-41ab-8a27-3c41d7472ea7
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 807e091838db20fdcf66a74fe3050cf192fab1e3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4953"></a>Предупреждение компилятора (уровень 1) C4953
"функция": выполнено редактирование встроенного кода после сбора данных профилирования, данные профилирования не используются  
  
 При использовании параметра [/LTCG:PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md)компилятор обнаружил входной модуль, который был перекомпилирован после `/LTCG:PGINSTRUMENT` , имеет измененную функцию (***функция***) и в котором выполняется тест, определивший функцию для встраивания. Однако после перекомпиляции модуля функция больше не является кандидатом для встраивания.  
  
 Это предупреждение носит информационный характер. Чтобы решить проблему, связанную с этим предупреждением, запустите `/LTCG:PGINSTRUMENT`, повторите все тестовые запуски и запустите `/LTCG:PGOPTIMIZE`.  
  
 Вместо этого предупреждения будет ошибка, если использовался параметр `/LTCG:PGOPTIMIZE` .