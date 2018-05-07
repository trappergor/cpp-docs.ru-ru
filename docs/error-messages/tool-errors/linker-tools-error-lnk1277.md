---
title: Ошибка средств компоновщика LNK1277 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1277
dev_langs:
- C++
helpviewer_keywords:
- LNK1277
ms.assetid: afca3de0-50cc-4140-af7a-13493a170835
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ec8f00793fcda748c60d9d8ea775611e3d025cd9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-error-lnk1277"></a>Ошибка средств компоновщика LNK1277
запись объекта не найдена в pgd (имя файла)  
  
 При использовании [/LTCG:PGOPTIMZE](../../build/reference/ltcg-link-time-code-generation.md), один из входных файлов LIB, def или OBJ путь отличался от пути, на котором они были найдены во время/LTCG: PGINSTRUMENT. Это может быть описано изменение переменной среды LIB после/LTCG: PGINSTRUMENT. Полный путь во входных файлах хранится в PGD-файл.  
  
 / LTCG: PGOPTIMIZE требует идентичности к этапу/LTCG: PGINSTRUMENT входные данные.  
  
 Чтобы устранить это предупреждение, выполните одно из следующих действий.  
  
-   Запустите/LTCG: PGINSTRUMENT, вернуть все тестовые запуски и запустите/LTCG: PGOPTIMIZE.  
  
-   Изменение значения переменной среды LIB в том случае если пользователь выполнял/LTCG: PGINSTRUMENT.  
  
 Обойти LNK1277, используя/LTCG: PGUPDATE не рекомендуется.