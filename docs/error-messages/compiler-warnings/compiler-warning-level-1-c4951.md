---
title: Предупреждение (уровень 1) C4951 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4951
dev_langs:
- C++
helpviewer_keywords:
- C4951
ms.assetid: 669d8bb7-5efa-4ba9-99db-4e65addbf054
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c3ebf012338bdf6b90cc943e754056335c6751a4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4951"></a>Предупреждение компилятора (уровень 1) C4951
"функция" была изменена после сбора данных профиля, данные профиля функции не используются  
  
 Функция была изменена во входном модуле при компоновке с параметром [/LTCG:PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md), поэтому данные профиля сейчас недопустимы. Входной модуль был повторно скомпилирован после компоновки с параметром **/LTCG:PGINSTRUMENT** и содержит функцию (***функция***) с другим потоком управления по сравнению с тем, что был в модуле во время компоновки с параметром **/LTCG:PGINSTRUMENT** .  
  
 Это предупреждение носит информационный характер. Чтобы устранить его, выполните компоновку с параметром **/LTCG:PGINSTRUMENT**, повторите все тестовые запуски и выполните компоновку с параметром **/LTCG:PGOPTIMIZE**.  
  
 Вместо этого предупреждения будет ошибка, если использовался параметр **/LTCG:PGOPTIMIZE** .