---
title: "Компилятор C4951 предупреждение (уровень 1) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4951
dev_langs:
- C++
helpviewer_keywords:
- C4951
ms.assetid: 669d8bb7-5efa-4ba9-99db-4e65addbf054
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
ms.openlocfilehash: 8317491a1649741c3322af3125fef80c0fb52f47
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4951"></a>Предупреждение компилятора (уровень 1) C4951
"функция" была изменена после сбора данных профиля, данные профиля функции не используются  
  
 Функция была изменена в модуле ввода в [/LTCG: PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md)таким образом, чтобы данные профиля теперь не является допустимым. Входной модуль был повторно скомпилирован после компоновки с параметром **/LTCG:PGINSTRUMENT** и содержит функцию (***функция***) с другим потоком управления по сравнению с тем, что был в модуле во время компоновки с параметром **/LTCG:PGINSTRUMENT** .  
  
 Это предупреждение носит информационный характер. Чтобы устранить его, выполните компоновку с параметром **/LTCG:PGINSTRUMENT**, повторите все тестовые запуски и выполните компоновку с параметром **/LTCG:PGOPTIMIZE**.  
  
 Вместо этого предупреждения будет ошибка, если использовался параметр **/LTCG:PGOPTIMIZE** .
