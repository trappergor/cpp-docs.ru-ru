---
title: Ошибка BSCMAKE BK1506 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- BK1506
dev_langs:
- C++
helpviewer_keywords:
- BK1506
ms.assetid: f51f8cea-f8fc-4323-bcf2-b7bd119792ee
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e19ec77818c8017387519b03e400c09d47021bc5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="bscmake-error-bk1506"></a>Ошибка BSCMAKE BK1506
не удается открыть файл «имя_файла» [: причина]  
  
 BSCMAKE не удается открыть файл.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.  
  
1.  Файл заблокирован другим процессом. Если `reason` говорит **отказано в разрешении**, браузер, использует этот файл. Закройте окно «Обзор» и повторите попытку сборки.  
  
2.  Диск переполнен.  
  
3.  Аппаратная ошибка.  
  
4.  Указанный выходной файл имеет имя, совпадающее с именем существующий подкаталог.