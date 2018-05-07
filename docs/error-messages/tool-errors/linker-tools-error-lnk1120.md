---
title: Ошибка средств компоновщика LNK1120 | Документы Microsoft
ms.custom: ''
ms.date: 05/17/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1120
dev_langs:
- C++
helpviewer_keywords:
- LNK1120
ms.assetid: 56aa7d36-921f-4daf-b44d-cca0d4fb1b51
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fab2b937f8bf941219c678c638e9757903ee7698
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-error-lnk1120"></a>Ошибка средств компоновщика LNK1120
*номер* неразрешенные внешние элементы  
  
Ошибка LNK1120 сообщает число (*номер*) ошибок неразрешенный внешний символ для этой операции связывания. Большинство неразрешенный внешний символ ошибки отображаются отдельно по [Ошибка средств компоновщика LNK2001](../../error-messages/tool-errors/linker-tools-error-lnk2001.md) и [Ошибка средств компоновщика LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md), который предшествовать это сообщение об ошибке, один раз для каждого неразрешенный внешний Ошибка символа.  
  
Чтобы устранить эту ошибку, исправьте все остальные неразрешенные внешние ошибки или другие ошибки компоновщика, расположенные перед ним в выходные данные построения. Эта ошибка не указывается, когда остается без неразрешенные внешние ошибок.  
