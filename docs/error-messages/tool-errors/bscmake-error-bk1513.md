---
title: Ошибка BSCMAKE BK1513 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- BK1513
dev_langs:
- C++
helpviewer_keywords:
- BK1513
ms.assetid: 9ba87c09-8d82-4c80-b0cf-a8de63dcf9da
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 93664a1224b85ec808805da0172aec408e875bc9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33295744"
---
# <a name="bscmake-error-bk1513"></a>Ошибка BSCMAKE BK1513
для неинкрементного обновления требуются все файлы .SBR  
  
 BSCMAKE не может создать новый BSC-файл, поскольку один или несколько SBR-файлов обрезаны. Чтобы найти имена обрезанных SBR-файлов, прочтите [BK4502](../../error-messages/tool-errors/bscmake-warning-bk4502.md) предупреждения, которые сопровождают данную ошибку.  
  
 BSCMAKE может обновить BSC-файл обрезанным SBR-файлом, но не сможет собрать новый. BSCMAKE может собрать новый BSC-файл по следующим причинам:  
  
-   BSC-файл отсутствует.  
  
-   Для BSC-файла указано неверное имя файла.  
  
-   BSC-файл поврежден.  
  
 Чтобы устранить эту проблему, нужно удалить обрезанные SBR-файлы и перестроить решение либо очистить решение, затем перестроить его. (В Интегрированной среде разработки выберите **построения**, **Очистить решение**и нажмите кнопку **построения**, **Перестроить решение**.)