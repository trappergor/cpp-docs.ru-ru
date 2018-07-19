---
title: Ошибка средств компоновщика LNK1200 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1200
dev_langs:
- C++
helpviewer_keywords:
- LNK1200
ms.assetid: 55771145-915e-4006-ac6c-ac702041eb2f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ab32939c55dce5e27f907f3d23e639b24741cdc3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33298828"
---
# <a name="linker-tools-error-lnk1200"></a>Ошибка средств компоновщика LNK1200
Ошибка при чтении базы данных программы «имя_файла»  
  
 Не удается прочитать базу данных программы (PDB).  
  
 Эта ошибка может быть вызвано повреждение файла.  
  
 Если `filename` является PDB для объектного файла, перекомпилировать файл объекта с помощью [/ZI](../../build/reference/z7-zi-zi-debug-information-format.md).  
  
 Если `filename` является PDB-ФАЙЛ для основного выходного файла, и эта ошибка возникает во время инкрементной компоновки, удалите PDB-ФАЙЛ и повторного создания связей.