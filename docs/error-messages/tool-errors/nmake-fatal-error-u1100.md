---
title: Неустранимая ошибка NMAKE U1100 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1100
dev_langs:
- C++
helpviewer_keywords:
- U1100
ms.assetid: c71910a7-c581-4d9c-a38c-d2d557d56289
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4d4ed57c980813c8539fbffed0e41a35048c0571
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="nmake-fatal-error-u1100"></a>Неустранимая ошибка NMAKE U1100
макрос «имя макроса» является недопустимым в контексте пакетного правила «правило»  
  
 NMAKE создает эту ошибку, если блок команд правила пакетного режима прямо или косвенно ссылается на макрос особый файл, который не является $<.  
  
 $< является единственным допустимым макрос для правила пакетного режима.