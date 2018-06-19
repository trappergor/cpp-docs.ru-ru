---
title: Предупреждение (уровень 1) C4952 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4952
dev_langs:
- C++
helpviewer_keywords:
- C4952
ms.assetid: 593324f0-5cfe-42fb-b221-2f71308765dd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 42696dfae816742c958bca23e25e311e834dd62a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33292146"
---
# <a name="compiler-warning-level-1-c4952"></a>Предупреждение компилятора (уровень 1) C4952
"функция": данные профилирования не найдены в базе данных программы "pgd-файл"  
  
 При использовании параметра [/LTCG: PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md)компилятор обнаружил модуль ввода, который был перекомпилирован после `/LTCG:PGINSTRUMENT` и имеет новую функцию (***функция***).  
  
 Это предупреждение носит информационный характер. Чтобы решить проблему, связанную с этим предупреждением, запустите `/LTCG:PGINSTRUMENT`, повторите все тестовые запуски и запустите `/LTCG:PGOPTIMIZE`.  
  
 Вместо этого предупреждения будет ошибка, если использовался параметр `/LTCG:PGOPTIMIZE` .