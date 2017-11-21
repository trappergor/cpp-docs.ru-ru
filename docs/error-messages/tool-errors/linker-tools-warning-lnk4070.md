---
title: "Предупреждение средств компоновщика LNK4070 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4070
dev_langs: C++
helpviewer_keywords: LNK4070
ms.assetid: f95f179a-fff9-427e-bd51-466b3934517f
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ca0a31fb3512b7b11150984fc3d15013cb75c0e0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-warning-lnk4070"></a>Предупреждение средств компоновщика LNK4070
Директива / out: в. EXP отличается от имени выходного файла «имя_файла»; директива игнорируется  
  
 `filename` Указано в [имя](../../build/reference/name-c-cpp.md) или [БИБЛИОТЕКИ](../../build/reference/library.md) инструкции при создании файла EXP, отличается от выходного `filename` , использованного по умолчанию или указан с [/OUT](../../build/reference/out-output-file-name.md) параметр.  
  
 Это предупреждение отображается, если изменить имя выходного файла, в среде разработки и где DEF-файл проекта не был обновлен. Вручную обновите DEF-файл, чтобы устранить это предупреждение.  
  
 Клиентской программы, которая использует результирующей библиотеки DLL могут возникнуть проблемы.