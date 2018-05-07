---
title: Предупреждение средств компоновщика LNK4070 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4070
dev_langs:
- C++
helpviewer_keywords:
- LNK4070
ms.assetid: f95f179a-fff9-427e-bd51-466b3934517f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9e4599e96552f1b98ef0b1af8d38995ebbe5a83e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-warning-lnk4070"></a>Предупреждение средств компоновщика LNK4070
Директива / out: в. EXP отличается от имени выходного файла «имя_файла»; директива игнорируется  
  
 `filename` Указано в [имя](../../build/reference/name-c-cpp.md) или [БИБЛИОТЕКИ](../../build/reference/library.md) инструкции при создании файла EXP, отличается от выходного `filename` , использованного по умолчанию или указан с [/OUT](../../build/reference/out-output-file-name.md) параметр.  
  
 Это предупреждение отображается, если изменить имя выходного файла, в среде разработки и где DEF-файл проекта не был обновлен. Вручную обновите DEF-файл, чтобы устранить это предупреждение.  
  
 Клиентской программы, которая использует результирующей библиотеки DLL могут возникнуть проблемы.