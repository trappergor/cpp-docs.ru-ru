---
title: Ошибка средств компоновщика LNK1164 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1164
dev_langs:
- C++
helpviewer_keywords:
- LNK1164
ms.assetid: da89765c-affa-4f88-b170-6d6b19a577cf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f85ad1c223c9d4b22e3763f1d24a6c2631f6342d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33297424"
---
# <a name="linker-tools-error-lnk1164"></a>Ошибка средств компоновщика LNK1164
раздел выравнивание разделов (number) больше, чем значение/ALIGN  
  
 Размер выравнивания для данного раздела в объектном файле превышает значение, указанное в [/ALIGN](../../build/reference/align-section-alignment.md) параметр. **/ALIGN** значение должно быть степенью числа 2 и равняться или превышать выравнивание раздела, заданное в объектном файле.  
  
 Перекомпилируйте с меньшего размера выравнивания раздела или увеличьте **/ALIGN** значение.