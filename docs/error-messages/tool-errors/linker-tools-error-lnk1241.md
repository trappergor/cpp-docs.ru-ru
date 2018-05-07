---
title: Ошибка средств компоновщика LNK1241 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1241
dev_langs:
- C++
helpviewer_keywords:
- LNK1241
ms.assetid: 7b8b52eb-0231-4521-b52a-2bce8d3e8956
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b02b1d9d06706c70478d958dd3c2af8dbc9c2c03
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-error-lnk1241"></a>Ошибка средств компоновщика LNK1241
файл ресурсов «файл ресурсов» уже указан  
  
 Эта ошибка возникает при запуске **cvtres** вручную из командной строки и затем передать OBJ-файл, полученный файл в компоновщик Кроме в других RES-файлы.  
  
 Чтобы задать несколько RES-файлов, следует передавать их компоновщику в виде RES-файлов, не OBJ-файлы созданных с помощью **cvtres**.