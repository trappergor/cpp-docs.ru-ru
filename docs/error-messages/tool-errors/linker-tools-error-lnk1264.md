---
title: "Ошибка средств компоновщика LNK1264 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1264
dev_langs: C++
helpviewer_keywords: LNK1264
ms.assetid: 23b1aad7-d382-42c1-bae8-db68575c57a8
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f590de75998becb9c03c73ac3083b04445a02156
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1264"></a>Ошибка средств компоновщика LNK1264
/ LTCG: PGINSTRUMENT указано, но не требуется создание кода; не удалось выполнить инструментирование  
  
 **/ LTCG: PGINSTRUMENT** был указан, но OBJ-файлы, скомпилированные с [/GL](../../build/reference/gl-whole-program-optimization.md). Инструментирование не могут принимать месте и отказ канала. Должен существовать хотя бы один OBJ-файл в командной строке, компилируется с помощью **/GL** , чтобы инструментирование могло произойти.  
  
 Профильная оптимизация (PGO) доступен только в 64-разрядных компиляторов.