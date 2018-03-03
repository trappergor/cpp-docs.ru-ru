---
title: "Ошибка средств компоновщика LNK1140 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK1140
dev_langs:
- C++
helpviewer_keywords:
- LNK1140
ms.assetid: 468d7651-a7cd-47b9-aead-5bb2fab56121
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a5a7bce157359d547f91ba2b560cf258e231b4a2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1140"></a>Ошибка средств компоновщика LNK1140
слишком много модулей для базы данных программы; связь с параметром/PDB: NONE  
  
 Проект содержит больше 4096 модулей.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>Возможные способы устранения этой ошибки  
  
1.  Перекомпоновка с помощью [/PDB: NONE](../../build/reference/pdb-use-program-database.md).  
  
2.  Скомпилируйте некоторые модули без отладочной информации.  
  
3.  Сократите число модулей.