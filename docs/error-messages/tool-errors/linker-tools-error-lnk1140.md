---
title: Ошибка средств компоновщика LNK1140 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1140
dev_langs:
- C++
helpviewer_keywords:
- LNK1140
ms.assetid: 468d7651-a7cd-47b9-aead-5bb2fab56121
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fc0d59589a1882aca4ef2deb419e1e4f1081e52b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33302741"
---
# <a name="linker-tools-error-lnk1140"></a>Ошибка средств компоновщика LNK1140
слишком много модулей для базы данных программы; связь с параметром/PDB: NONE  
  
 Проект содержит больше 4096 модулей.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>Возможные способы устранения этой ошибки  
  
1.  Перекомпоновка с помощью [/PDB: NONE](../../build/reference/pdb-use-program-database.md).  
  
2.  Скомпилируйте некоторые модули без отладочной информации.  
  
3.  Сократите число модулей.