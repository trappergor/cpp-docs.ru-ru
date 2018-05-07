---
title: Ошибка средств компоновщика LNK2027 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2027
dev_langs:
- C++
helpviewer_keywords:
- LNK2027
ms.assetid: e2f857a8-8e8a-4697-bbff-12ccb84a35c1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 156310a0d21651b9fd2ee6002ace419db4996681
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-error-lnk2027"></a>Ошибка средств компоновщика LNK2027
ссылка на неразрешенный модуля «модуль»  
  
 Файл, переданный компоновщику имеет зависимость от модуля, который не был задан с **/ASSEMBLYMODULE** и не передан компоновщику.  
  
 Чтобы устранить ошибку LNK2027, выполните одно из следующих действий.  
  
-   Не передавайте компоновщику файл, который зависит от модуля.  
  
-   Укажите модуль с **/ASSEMBLYMODULE**.  
  
-   Если модуль является безопасным .netmodule, передайте модуль непосредственно в компоновщик.  
  
 Дополнительные сведения см. в разделе [/ASSEMBLYMODULE (Добавление модуля MSIL в сборку)](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md) и [.netmodule качестве входных файлов компоновщика](../../build/reference/netmodule-files-as-linker-input.md).