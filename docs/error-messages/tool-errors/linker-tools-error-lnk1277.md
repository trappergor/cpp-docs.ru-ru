---
title: "Ошибка средств компоновщика LNK1277 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1277
dev_langs: C++
helpviewer_keywords: LNK1277
ms.assetid: afca3de0-50cc-4140-af7a-13493a170835
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3606207afc197dc26ac0540d476b74f52c0dc0a9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1277"></a>Ошибка средств компоновщика LNK1277
запись объекта не найдена в pgd (имя файла)  
  
 При использовании [/LTCG:PGOPTIMZE](../../build/reference/ltcg-link-time-code-generation.md), один из входных файлов LIB, def или OBJ путь отличался от пути, на котором они были найдены во время/LTCG: PGINSTRUMENT. Это может быть описано изменение переменной среды LIB после/LTCG: PGINSTRUMENT. Полный путь во входных файлах хранится в PGD-файл.  
  
 / LTCG: PGOPTIMIZE требует идентичности к этапу/LTCG: PGINSTRUMENT входные данные.  
  
 Чтобы устранить это предупреждение, выполните одно из следующих действий.  
  
-   Запустите/LTCG: PGINSTRUMENT, вернуть все тестовые запуски и запустите/LTCG: PGOPTIMIZE.  
  
-   Изменение значения переменной среды LIB в том случае если пользователь выполнял/LTCG: PGINSTRUMENT.  
  
 Обойти LNK1277, используя/LTCG: PGUPDATE не рекомендуется.