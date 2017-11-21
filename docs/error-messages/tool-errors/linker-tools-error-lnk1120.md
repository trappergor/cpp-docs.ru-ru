---
title: "Ошибка средств компоновщика LNK1120 | Документы Microsoft"
ms.custom: 
ms.date: 05/17/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1120
dev_langs: C++
helpviewer_keywords: LNK1120
ms.assetid: 56aa7d36-921f-4daf-b44d-cca0d4fb1b51
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: dafecac08499bea0571b2f48015e50570229d889
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-error-lnk1120"></a>Ошибка средств компоновщика LNK1120
*номер* неразрешенные внешние элементы  
  
Ошибка LNK1120 сообщает число (*номер*) ошибок неразрешенный внешний символ для этой операции связывания. Большинство неразрешенный внешний символ ошибки отображаются отдельно по [Ошибка средств компоновщика LNK2001](../../error-messages/tool-errors/linker-tools-error-lnk2001.md) и [Ошибка средств компоновщика LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md), который предшествовать это сообщение об ошибке, один раз для каждого неразрешенный внешний Ошибка символа.  
  
Чтобы устранить эту ошибку, исправьте все остальные неразрешенные внешние ошибки или другие ошибки компоновщика, расположенные перед ним в выходные данные построения. Эта ошибка не указывается, когда остается без неразрешенные внешние ошибок.  
