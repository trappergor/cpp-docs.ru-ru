---
title: "Предупреждение (уровень 1) C4951 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4951
dev_langs: C++
helpviewer_keywords: C4951
ms.assetid: 669d8bb7-5efa-4ba9-99db-4e65addbf054
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 199df135d5d2c00255037e5a1b31db80e2683d4f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4951"></a>Предупреждение компилятора (уровень 1) C4951
"функция" была изменена после сбора данных профиля, данные профиля функции не используются  
  
 Функция была изменена во входном модуле при компоновке с параметром [/LTCG:PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md), поэтому данные профиля сейчас недопустимы. Входной модуль был повторно скомпилирован после компоновки с параметром **/LTCG:PGINSTRUMENT** и содержит функцию (***функция***) с другим потоком управления по сравнению с тем, что был в модуле во время компоновки с параметром **/LTCG:PGINSTRUMENT** .  
  
 Это предупреждение носит информационный характер. Чтобы устранить его, выполните компоновку с параметром **/LTCG:PGINSTRUMENT**, повторите все тестовые запуски и выполните компоновку с параметром **/LTCG:PGOPTIMIZE**.  
  
 Вместо этого предупреждения будет ошибка, если использовался параметр **/LTCG:PGOPTIMIZE** .